---
layout: page
title: Join a Match
permalink: /join/
---

<div id="join">
  <p>Someone is starting a Two-Phone Match in Pongle. You each score your own Points from your own phone, with your own Flic or Apple Watch, and both phones show the score.</p>

  <p id="join-open-line" hidden><a id="join-open" class="join-button" href="#">Join in Pongle</a></p>

  <p id="join-missing" hidden>This link is missing its Join code. Ask the other player to show the code again.</p>
</div>

## Don't have Pongle yet?

Pongle is in testing on TestFlight. Ask the other player to add you as a tester, install Pongle, then scan the code again. In Pongle you can also scan it yourself: open the settings dock and choose **Two-Phone Match → Scan a Join Code**.

Joining needs Pongle 1.1 or later. If Pongle opens but nothing happens, update it from TestFlight.

You'll sign in with your email before Joining. The code works only until a phone Joins. Joining puts each of you on the other's Roster, so Matches you play together, on two phones or on one, count for both of you. Either of you can Leave that later.

<style>
  .join-button {
    display: inline-block;
    padding: 0.7em 1.4em;
    border-radius: 12px;
    background: #fa8f33;
    color: #111 !important;
    font-weight: 700;
    text-decoration: none !important;
  }
</style>

<script>
  (function () {
    // Only a UUID, as Pongle reads a Join code; never written as HTML.
    var raw = new URLSearchParams(window.location.search).get("code") || "";
    var code = raw.toLowerCase();
    if (!/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/.test(code)) {
      document.getElementById("join-missing").hidden = false;
      return;
    }
    document.getElementById("join-open").href = "pongle://join?code=" + encodeURIComponent(code);
    document.getElementById("join-open-line").hidden = false;
  })();
</script>
