---
layout: page
title: Play later?
permalink: /meetup/
---

<div id="meetup">
  <p>Someone has planned a game of table tennis with you in Pongle: a Table and a time. Open it in Pongle to see who, where and when, and to say yes or no.</p>

  <p id="meetup-open-line" hidden><a id="meetup-open" class="meetup-button" href="#">Open in Pongle</a></p>

  <p id="meetup-missing" hidden>This link is missing its Meetup. Ask whoever sent it to send it again.</p>
</div>

## Don't have Pongle yet?

Pongle is in testing on TestFlight. Ask the person who sent this to add you as a tester, install Pongle, then come back to this page and tap **Open in Pongle**. Meetups need the latest Pongle; if Pongle opens but nothing happens, update it from TestFlight.

If a calendar file came with the link, you can add it to your calendar now. You'll sign in with your email before answering. Once you **Accept**, you see exactly where the Table is, and each of you is put on the other's list, so matches you play together count for both of you. Either of you can Leave that later.

<style>
  .meetup-button {
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
    // Only a UUID, as Pongle reads a Meetup's code; never written as HTML.
    var raw = new URLSearchParams(window.location.search).get("code") || "";
    var code = raw.toLowerCase();
    if (!/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/.test(code)) {
      document.getElementById("meetup-missing").hidden = false;
      return;
    }
    document.getElementById("meetup-open").href = "pongle://meetup?code=" + encodeURIComponent(code);
    document.getElementById("meetup-open-line").hidden = false;
  })();
</script>
