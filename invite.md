---
layout: page
title: You're invited
permalink: /invite/
---

<div id="invite">
  <p>Someone has been recording your table tennis matches in Pongle and invited you to Claim them, so they show in your own Match History too.</p>

  <p id="invite-code-line" hidden>Your Invite code: <strong id="invite-code" style="font-family: ui-monospace, Menlo, monospace; font-size: 1.3em; letter-spacing: 0.05em;"></strong></p>

  <p id="invite-open-line" hidden><a id="invite-open" class="invite-button" href="#">Open in Pongle</a></p>

  <p id="invite-missing" hidden>This link is missing its Invite code. Ask whoever sent it to send it again.</p>
</div>

## Don't have Pongle yet?

Pongle is in testing on TestFlight. Ask the person who invited you to add you as a tester, install Pongle, then come back to this page and tap **Open in Pongle**. You can also type the code yourself: in Pongle, open the settings dock and choose **Account → Enter an Invite code**.

You'll sign in with your email before accepting. The Invite works once and expires 7 days after it was sent. Nothing is shared until you accept.

<style>
  .invite-button {
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
    // Only letters and digits, as Pongle reads a code; never written as HTML.
    var raw = new URLSearchParams(window.location.search).get("code") || "";
    var code = raw.toUpperCase().replace(/[^0-9A-Z]/g, "").slice(0, 10);
    if (code.length !== 10) {
      document.getElementById("invite-missing").hidden = false;
      return;
    }
    document.getElementById("invite-code").textContent = code.slice(0, 5) + "-" + code.slice(5);
    document.getElementById("invite-code-line").hidden = false;
    document.getElementById("invite-open").href = "pongle://invite?code=" + encodeURIComponent(code);
    document.getElementById("invite-open-line").hidden = false;
  })();
</script>
