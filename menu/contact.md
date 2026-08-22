---
layout: page
title: Contact
permalink: /contact
---

If you have any questions or problems, feel free to email me.

<i class="fa fa-map-marker" aria-hidden="true" style="color: #2b6cb0;"></i> Currently in Guangzhou, China
<span class="contact-clock"><i class="fa fa-clock-o" aria-hidden="true" style="color: #2b6cb0;"></i> Local time in Guangzhou: <span id="guangzhou-clock">--:--:--</span> <span class="clock-date" id="guangzhou-clock-date"></span> <span class="clock-tz">(UTC+8)</span></span>

<style>
.contact-clock { display: inline-block; font-size: 0.9em; color: #444; vertical-align: middle; }
.clock-date { color: #888; }
.clock-tz { color: #aaa; font-size: 0.85em; }
</style>

<script>
(function () {
  function update() {
    var fmt = new Intl.DateTimeFormat('en-GB', {
      timeZone: 'Asia/Shanghai',
      weekday: 'short', year: 'numeric', month: 'short', day: '2-digit',
      hour: '2-digit', minute: '2-digit', second: '2-digit',
      hourCycle: 'h23'
    });
    var parts = fmt.formatToParts(new Date());
    var get = function (t) { var p = parts.find(function (x) { return x.type === t; }); return p ? p.value : ''; };
    var timeStr = get('hour') + ':' + get('minute') + ':' + get('second');
    var dateStr = get('weekday') + ', ' + get('day') + ' ' + get('month') + ' ' + get('year');
    var el = document.getElementById('guangzhou-clock');
    var elDate = document.getElementById('guangzhou-clock-date');
    if (el) { el.textContent = timeStr; }
    if (elDate) { elDate.textContent = dateStr; }
  }
  update();
  setInterval(update, 1000);
})();
</script>

<iframe src="https://www.google.com/maps?q=Guangzhou,%20China&z=12&hl=en&output=embed" width="100%" height="300" style="border: 1px solid #ddd; border-radius: 6px;" allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
