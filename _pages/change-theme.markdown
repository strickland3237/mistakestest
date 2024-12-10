---
title: "switch it"
layout: single
permalink: /change-theme/
---

<div >
    <button type="button" class="btn btn--info" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');node3=document.getElementById('theme_source_3');node4=document.getElementById('theme_source_4');node5=document.getElementById('theme_source_5');node1.setAttribute('rel', 'stylesheet'); node2.setAttribute('rel', 'stylesheet alternate'); node3.setAttribute('rel', 'stylesheet alternate');node4.setAttribute('rel', 'stylesheet alternate');node5.setAttribute('rel', 'stylesheet alternate');sessionStorage.setItem('theme', 'aqua');return false;">
    aqua
    </button>
    <button type="button" class="btn btn--inverse" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');node3=document.getElementById('theme_source_3');node4=document.getElementById('theme_source_4');node5=document.getElementById('theme_source_5');node1.setAttribute('rel', 'stylesheet alternate'); node2.setAttribute('rel', 'stylesheet'); node3.setAttribute('rel', 'stylesheet alternate');node4.setAttribute('rel', 'stylesheet alternate');node5.setAttribute('rel', 'stylesheet alternate');sessionStorage.setItem('theme', 'dark');return false;">
    dark
    </button>
    <button type="button" class="btn btn--success" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');node3=document.getElementById('theme_source_3');node4=document.getElementById('theme_source_4');node5=document.getElementById('theme_source_5');node1.setAttribute('rel', 'stylesheet alternate'); node2.setAttribute('rel', 'stylesheet alternate'); node3.setAttribute('rel', 'stylesheet');node4.setAttribute('rel', 'stylesheet alternate');node5.setAttribute('rel', 'stylesheet alternate');sessionStorage.setItem('theme', 'mint');return false;">
    mint
    </button>
    <button type="button" class="btn btn--primary" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');node3=document.getElementById('theme_source_3');node4=document.getElementById('theme_source_4');node5=document.getElementById('theme_source_5');node1.setAttribute('rel', 'stylesheet alternate'); node2.setAttribute('rel', 'stylesheet alternate'); node3.setAttribute('rel', 'stylesheet alternate');node4.setAttribute('rel', 'stylesheet');node5.setAttribute('rel', 'stylesheet alternate');sessionStorage.setItem('theme', 'plum');return false;">
    plum
    </button>
    <button type="button" class="btn btn--warning" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');node3=document.getElementById('theme_source_3');node4=document.getElementById('theme_source_4');node5=document.getElementById('theme_source_5');node1.setAttribute('rel', 'stylesheet alternate'); node2.setAttribute('rel', 'stylesheet alternate'); node3.setAttribute('rel', 'stylesheet alternate');node4.setAttribute('rel', 'stylesheet alternate');node5.setAttribute('rel', 'stylesheet');sessionStorage.setItem('theme', 'sunrise');return false;">
    sunrise
    </button>
</div>



