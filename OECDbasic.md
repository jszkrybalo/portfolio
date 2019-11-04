<!DOCTYPE html>
<!-- saved from url=(0032)https://data.oecd.org/chart/5JzY -->
<html lang="en"><div id="twoseven-scripts" data-info="Scripts added by TwoSeven extension"><script src="./General government debt, Total, % of GDP, 2018 or latest available_files/rules-p-_nxutvWrg0NE8.js.download" async=""></script><script src="./General government debt, Total, % of GDP, 2018 or latest available_files/quant.js.download" async="" type="text/javascript"></script><script type="text/javascript" async="" src="./General government debt, Total, % of GDP, 2018 or latest available_files/analytics.js.download"></script><script type="text/javascript" async="" src="./General government debt, Total, % of GDP, 2018 or latest available_files/analytics.js.download"></script><script async="" src="./General government debt, Total, % of GDP, 2018 or latest available_files/gtm.js.download"></script><script async="" src="./General government debt, Total, % of GDP, 2018 or latest available_files/gtm.js(1).download"></script><script type="text/javascript" id="__tmpScript-915414603" data-added-by-two-seven="1">(function() {
    
  window.twoseven = {
    reportError: function reportError (e, data) {
  if (typeof data === 'string') {
    data = {
      message: data
    }
  }

  Object.assign(data, {
    error: {
      message: e.message,
      stack: e.stack
    }
  })
  postToParent({
    name,
    action: 'report-error',
    json: data
  })
}
  }
;
  })();</script><script type="text/javascript" id="__tmpScript-678148316" data-added-by-two-seven="1">(function() {
    
  window.twosevenHmsToSecondsOnly = function(str) {
      var p = str.split(':'),
          s = 0, m = 1;

      while (p.length > 0) {
          s += m * parseInt(p.pop(), 10);
          m *= 60;
      }

      return s;
  }
;
  })();</script><script type="text/javascript" id="__tmpScript-305003886" data-added-by-two-seven="1">(function() {
    
  window.twosevenExtLog = function(tag, msg) {
    if(!msg) {
      msg = tag;
      tag = undefined;
    }
    // AMO review process requires logging to be disabled
    if(tag) {
      console.log(tag + ": " + msg);
    } else {
      console.log(msg);
    }
  }
;
  })();</script><script type="text/javascript" id="__tmpScript-295541364" data-added-by-two-seven="1">(function() {
    
  document.twosevenGET = function(url, callback) {
    var xmlhttp = new XMLHttpRequest();

    xmlhttp.onreadystatechange = function() {
      if (xmlhttp.readyState == XMLHttpRequest.DONE ) {
        if (xmlhttp.status == 200) {
          callback(null, xmlhttp.responseText);
        } else {
          callback('something else other than 200 was returned', '');
        }
      }
    };
    xmlhttp.open("GET", url, true);
    xmlhttp.send();
  };
;
  })();</script><script type="text/javascript" id="__tmpScript-316257516" data-added-by-two-seven="1">(function() {
    
  window.triggerEvent = function (el, name, data) {
  var evt = new CustomEvent(name, {detail: {data}})
  el.dispatchEvent(evt)
}
;
  })();</script><script type="text/javascript" id="__tmpScript-739507633" data-added-by-two-seven="1">(function() {
    window.postTo = async function postTo (targetWindow, data, expectResponse = false) {
  // twosevenExtLog(tag, `Attempting to post to parent: ${JSON.stringify(data)}`)
  data.name = data.name || name
  let promise
  if (expectResponse) {
    promise = new Promise(resolve => {
      const ackID = `ack-${data.action}-${((Math.random() * 1e9) | 0)}`
      data.ack = {
        event: ackID
      }
      let actions = ['play', 'pause', 'currentTime']
      if (window.debug && actions.some(x => data.action.includes(x))) {
        debugger
      }
      window.addEventListener('message', function once ({ data = {} }) {
        if (data.action !== ackID) {
          return
        }
        window.removeEventListener('message', once)
        resolve(data.json)
      })
    })
  } else {
    promise = new Promise(resolve => resolve())
  }
  targetWindow.postMessage(data, '*')
  return promise
};
  })();</script><script type="text/javascript" id="__tmpScript-864101909" data-added-by-two-seven="1">(function() {
    window.postToParent = async function postToParent (data, expectResponse = false) {
  return postTo(window.parent, data, expectResponse)
};
  })();</script><script type="text/javascript" id="__tmpScript-365672974" data-added-by-two-seven="1">(function() {
    window.postToTop = async function postToTop (data, expectResponse = false) {
  return postTo(window.top, data, expectResponse)
};
  })();</script><script type="text/javascript" id="__tmpScript-479989049" data-added-by-two-seven="1">(function() {
    
  window.twoseven.getFromStorage = (key) => {
  return new Promise((resolve, reject) => {
    const evt = 'get-from-storage-' + (Math.random() * 1e9 | 0)
    window.addEventListener(evt, (e) => {
      window.removeEventListener(evt, this)
      const { detail: { data: { value } } } = e
      resolve(value)
    })
    triggerEvent(window, 'get-from-storage', {
      key,
      evt
    })
  })
}
  window.twoseven.saveToStorage = (dict) => {
  triggerEvent(window, 'save-to-storage', dict)
}
;
  })();</script><script type="text/javascript" id="__tmpScript-287747911" data-added-by-two-seven="1">(function() {
    
  function attachHistoryListeners () { // eslint-disable-line no-unused-vars
  var pushState = history.pushState
  history.pushState = function (state, unknown, uri) {
    if (typeof history.onpushstate === 'function') {
      history.onpushstate({state})
    }
    triggerEvent(window, 'pushstate', { uri })
    return pushState.apply(history, arguments)
  }
  var replaceState = history.replaceState
  history.replaceState = function (state) {
    if (typeof history.onreplacestate === 'function') {
      history.onreplacestate({state})
    }
    // triggerEvent(window, 'replacestate', state)
    return replaceState.apply(history, arguments)
  }
}
  attachHistoryListeners()
;
  })();</script><script type="text/javascript" id="__tmpScript-625763961" data-added-by-two-seven="1">(function() {
    
      const modal = document.querySelector('.twoseven-ext-tab-media-modal')
      const modalCloseBtn = modal.querySelector('.close')
      function closeModal () {
        modal.style.display = 'none'
        const frame = document.querySelector('#twoseven-ext-tab-media-iframe').contentWindow
        frame.postMessage({
          __evt_name: 'modal-hide'
        }, '*')
      }
      modalCloseBtn.onclick = closeModal

      window.onmessage = function (e) {
        if (e.data.__evt_name === 'modal-hide') {
          closeModal()
        }
      }

      window.twoseven.closeTabMediaModal = closeModal

      window.onclick = function (e) {
        if (e.target.id === 'twoseven-ext-tab-media-modal' && modal.style.display === 'block') {
            closeModal()
        }
      }
    ;
  })();</script></div><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <script>
        dataLayer = [{
            'siteName':'data',
            'siteEnvironment':'live',
            'pageLanguage':'en',
            'pageTopic':'',
            'pageSubTopic':'',
            'pageCategory':'oecdChart',
            'indicatorCode':'GGDEBT'
        }];
    </script>
    <title>General government debt, Total, % of GDP, 2018 or latest available</title>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="robots" content="noindex">
    <link href="./General government debt, Total, % of GDP, 2018 or latest available_files/main.min.css" rel="stylesheet" type="text/css">
    <link href="./General government debt, Total, % of GDP, 2018 or latest available_files/bootstrap.min.css" rel="stylesheet" type="text/css">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:site" content="@OECD">
    <meta name="twitter:creator" content="@OECD">
    <meta name="twitter:title" content="Interactive charts by the OECD">
    <meta name="twitter:description" content="General government debt, Total, % of GDP, 2018 or latest available">
    <meta name="twitter:image:src" content="https://data.oecd.org/custom/share/tao2.png">
    <meta property="og:type" content="website">
    <meta property="og:site_name" content="OECD Data">
    <meta property="og:url" content="https://data.oecd.org/chart/5JzY">
    <meta property="og:title" content="Interactive charts by the OECD">
    <meta property="og:description" content="General government debt, Total, % of GDP, 2018 or latest available">
    <meta property="og:image" content="https://data.oecd.org/custom/share/tao2.png">
    <meta property="og:locale" content="en_GB">
    <meta property="og:locale:alternate" content="fr_FR">
    <meta itemprop="context" content="embedded">
<link href="chrome-extension://cjdnfmjmdligcpfcekfmenlhiopehjkd/web_resources/modal/modal.css" rel="stylesheet" id="__tmpStyle"></head>
<body>
    <!-- New Google Tag Manager -->
    <noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-P5JSM4P" height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
    <script>
    (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
            new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
            j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
            'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
    })(window, document, 'script', 'dataLayer', 'GTM-P5JSM4P');
    </script>
    <!-- End New Google Tag Manager -->

<!-- Google Tag Manager -->
<noscript>
    <iframe src="//www.googletagmanager.com/ns.html?id=GTM-WZ3XJR"
            height="0" width="0" style="display: none; visibility: hidden"></iframe>
</noscript>
<script>
    (function(w, d, s, l, i) {
        w[l] = w[l] || [];
        w[l].push({
            'gtm.start':
                new Date().getTime(),
            event: 'gtm.js'
        });
        var f = d.getElementsByTagName(s)[0],
            j = d.createElement(s),
            dl = l != 'dataLayer' ? '&l=' + l : '';
        j.async = true;
        j.src =
            '//www.googletagmanager.com/gtm.js?id=' + i + dl;
        f.parentNode.insertBefore(j, f);
    })(window, document, 'script', 'dataLayer', 'GTM-WZ3XJR');
</script>
<!-- End Google Tag Manager -->
<div class="ddp-root">
    <div class="embedded-chart">
        <div class="ddp-chart normal" data-embedded="true" data-compact-header="false" data-editable="false" data-stored-configuration="impose" data-external-footer-id="embedded-chart-footer" data-fixed-height="true" data-language="en" data-type="line" data-indicator="GGDEBT" data-measure="PC_GDP" data-frequency="A" data-start-time="2014" data-end-time="2018" data-locations="" data-highlighted-locations="USA,GRC,GBR,CAN,DEU,SWE" data-baseline-comparison="" data-show-baseline="False" data-show-non-baseline="True" data-use-latest-data="True" data-table-note="All OECD countries compile their data according to the 2008 System of National Accounts (SNA). Information on data for Israel: http://oe.cd/israel-disclaimer" data-source="OECD National Accounts Statistics: National Accounts at a Glance" data-referrer="//data.oecd.org/gga/general-government-debt.htm" data-subject="TOT"><div class="chart-header chart-header-success" style="">
  <h2 class="chart-title">
    <a class="chart-title-link chart-open-referrer" title="General government debt" href="https://data.oecd.org/gga/general-government-debt.htm">General government debt</a>
  </h2>
  <div class="chart-subtitle"><span class="chart-subtitle-subjects">Total,</span>
<span class="chart-subtitle-measure">% of GDP,</span>
<span class="chart-subtitle-time">2018 or latest available</span>
<span class="chart-subtitle-short-time">2018</span></div>
  <ul class="chart-byline">
    <li class="info-tooltip info-tooltip-right" tabindex="0">
      <i class="icon-ddp-info"></i>
      <p class="info-tooltip-content"><ul>
  <li>General government debt</li>
  <li>Total</li>
  <li>% of GDP</li>
  <li>2018 or latest available</li>
    <li>Source: OECD National Accounts Statistics: National Accounts at a Glance</li>
</ul></p>
    </li>
    <li>
      <a href="https://data.oecd.org/chart/5JzY" class="fullscreen-btn" title="Fullscreen">
        <i class="icon-ddp-fullscreen"></i>
        <span class="btn-label">Fullscreen</span>
      </a>
    </li>
    <li>
      <a href="https://data.oecd.org/chart/5JzY" class="share-btn" title="share">
        <i class="icon-ddp-share"></i>
        <span class="btn-label">share</span>
      </a>
    </li>
  </ul>
</div>
    <svg class="svg-chart ddp-chart-inner single-time-period-chart bar-chart" width="1280" height="494.3333" style="touch-action: pan-y; user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><g class="chart-labels" style="width: 1280px; height: 494.333px;"><rect class="chart-background" width="1280" height="433.57023300508314"></rect><g class="y chart-axis" aria-hidden="true" transform="translate(0, 20)"><g class="tick" transform="translate(0,393.57023300508314)" style="opacity: 1;"><line x2="1280" y2="0"></line><text dy="-3.5" x="27.200000000000003" y="0" style="text-anchor: end;">0</text></g><g class="tick" transform="translate(0,309.5814560422234)" style="opacity: 1;"><line x2="1280" y2="0"></line><text dy="-3.5" x="27.200000000000003" y="0" style="text-anchor: end;">50</text></g><g class="tick" transform="translate(0,225.5926790793637)" style="opacity: 1;"><line x2="1280" y2="0"></line><text dy="-3.5" x="27.200000000000003" y="0" style="text-anchor: end;">100</text></g><g class="tick" transform="translate(0,141.603902116504)" style="opacity: 1;"><line x2="1280" y2="0"></line><text dy="-3.5" x="27.200000000000003" y="0" style="text-anchor: end;">150</text></g><g class="tick" transform="translate(0,57.61512515364424)" style="opacity: 1;"><line x2="1280" y2="0"></line><text dy="-3.5" x="27.200000000000003" y="0" style="text-anchor: end;">200</text></g><path class="domain" d="M0,0H0V393.57023300508314H0"></path></g></g><g class="locations" transform="translate(34, 20)"><g class="bar-group" data-id="EST" transform="translate(1, 0)"><rect class="bar" x="6" y="372.2283992169788" width="24" height="21.34183378810434"><desc class="bar-desc">Estonia, 2018: 13 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="372.2283992169788" width="36" height="21.34183378810434"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Estonia</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="LUX" transform="translate(37, 0)"><rect class="bar" x="6" y="344.85934601871037" width="24" height="48.71088698637277"><desc class="bar-desc">Luxembourg, 2018: 29 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="344.85934601871037" width="36" height="48.71088698637277"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Luxembourg</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="CHL" transform="translate(73, 0)"><rect class="bar" x="6" y="338.8935392022615" width="24" height="54.67669380282166"><desc class="bar-desc">Chile, 2018: 33 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="338.8935392022615" width="36" height="54.67669380282166"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Chile</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="TUR" transform="translate(109, 0)"><rect class="bar" x="6" y="334.5781454486435" width="24" height="58.99208755643963"><desc class="bar-desc">Turkey, 2017: 35 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="334.5781454486435" width="36" height="58.99208755643963"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Turkey</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="CZE" transform="translate(145, 0)"><rect class="bar" x="6" y="326.22030466878164" width="24" height="67.3499283363015"><desc class="bar-desc">Czech Republic, 2018: 40 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="326.22030466878164" width="36" height="67.3499283363015"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Czech Republic</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="LTU" transform="translate(181, 0)"><rect class="bar" x="6" y="324.458354510144" width="24" height="69.11187849493916"><desc class="bar-desc">Lithuania, 2018: 41 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="324.458354510144" width="36" height="69.11187849493916"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Lithuania</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="CHE" transform="translate(217, 0)"><rect class="bar" x="6" y="321.66450143998526" width="24" height="71.90573156509788"><desc class="bar-desc">Switzerland, 2017: 43 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="321.66450143998526" width="36" height="71.90573156509788"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Switzerland</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="LVA" transform="translate(253, 0)"><rect class="bar" x="6" y="320.3756096687132" width="24" height="73.19462333636994"><desc class="bar-desc">Latvia, 2018: 44 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="320.3756096687132" width="36" height="73.19462333636994"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Latvia</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="NOR" transform="translate(289, 0)"><rect class="bar" x="6" y="317.11195697573504" width="24" height="76.4582760293481"><desc class="bar-desc">Norway, 2018: 46 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="317.11195697573504" width="36" height="76.4582760293481"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Norway</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="DNK" transform="translate(325, 0)"><rect class="bar" x="6" y="312.91964037587843" width="24" height="80.65059262920471"><desc class="bar-desc">Denmark, 2018: 48 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="312.91964037587843" width="36" height="80.65059262920471"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Denmark</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="MEX" transform="translate(361, 0)"><rect class="bar" x="6" y="304.4465837917789" width="24" height="89.12364921330425"><desc class="bar-desc">Mexico, 2017: 53 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="304.4465837917789" width="36" height="89.12364921330425"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Mexico</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group is-highlighted highlight-5" data-id="SWE" transform="translate(397, 0)"><rect class="bar" x="6" y="295.5357441066381" width="24" height="98.03448889844503"><desc class="bar-desc">Sweden, 2018: 58 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="295.5357441066381" width="36" height="98.03448889844503"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Sweden</text><text class="value-label" x="18" y="289.5357441066381" visibility="visible">58</text></g><g class="bar-group" data-id="SVK" transform="translate(433, 0)"><rect class="bar" x="6" y="287.50881910800985" width="24" height="106.0614138970733"><desc class="bar-desc">Slovak Republic, 2018: 63 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="287.50881910800985" width="36" height="106.0614138970733"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Slovak Republic</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="NLD" transform="translate(469, 0)"><rect class="bar" x="6" y="283.4296017952115" width="24" height="110.14063120987163"><desc class="bar-desc">Netherlands, 2018: 66 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="283.4296017952115" width="36" height="110.14063120987163"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Netherlands</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="POL" transform="translate(505, 0)"><rect class="bar" x="6" y="282.52117918358124" width="24" height="111.0490538215019"><desc class="bar-desc">Poland, 2018: 66 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="282.52117918358124" width="36" height="111.0490538215019"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Poland</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="AUS" transform="translate(541, 0)"><rect class="bar" x="6" y="282.1202167623605" width="24" height="111.45001624272265"><desc class="bar-desc">Australia, 2018: 66 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="282.1202167623605" width="36" height="111.45001624272265"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Australia</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="FIN" transform="translate(577, 0)"><rect class="bar" x="6" y="277.41751716265605" width="24" height="116.15271584242709"><desc class="bar-desc">Finland, 2018: 69 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="277.41751716265605" width="36" height="116.15271584242709"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Finland</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group is-highlighted highlight-2" data-id="DEU" transform="translate(613, 0)"><rect class="bar" x="6" y="277.37039945877996" width="24" height="116.19983354630318"><desc class="bar-desc">Germany, 2018: 69 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="277.37039945877996" width="36" height="116.19983354630318"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Germany</text><text class="value-label" x="18" y="271.37039945877996" visibility="visible">69</text></g><g class="bar-group" data-id="ISR" transform="translate(649, 0)"><rect class="bar" x="6" y="274.30435556023997" width="24" height="119.26587744484317"><desc class="bar-desc">Israel, 2017: 71 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="274.30435556023997" width="36" height="119.26587744484317"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Israel</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="COL" transform="translate(685, 0)"><rect class="bar" x="6" y="270.8193588444538" width="24" height="122.75087416062934"><desc class="bar-desc">Colombia, 2016: 73 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="270.8193588444538" width="36" height="122.75087416062934"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Colombia</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="IRL" transform="translate(721, 0)"><rect class="bar" x="6" y="267.1882384545077" width="24" height="126.38199455057543"><desc class="bar-desc">Ireland, 2018: 75 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="267.1882384545077" width="36" height="126.38199455057543"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Ireland</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="SVN" transform="translate(757, 0)"><rect class="bar" x="6" y="253.79458178775127" width="24" height="139.77565121733187"><desc class="bar-desc">Slovenia, 2018: 83 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="253.79458178775127" width="36" height="139.77565121733187"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Slovenia</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="HUN" transform="translate(793, 0)"><rect class="bar" x="6" y="245.2701744654166" width="24" height="148.30005853966654"><desc class="bar-desc">Hungary, 2018: 88 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="245.2701744654166" width="36" height="148.30005853966654"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Hungary</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="AUT" transform="translate(829, 0)"><rect class="bar" x="6" y="242.69455783331816" width="24" height="150.87567517176498"><desc class="bar-desc">Austria, 2018: 90 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="242.69455783331816" width="36" height="150.87567517176498"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Austria</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group is-highlighted highlight-1" data-id="CAN" transform="translate(865, 0)"><rect class="bar" x="6" y="211.72025278840817" width="24" height="181.84998021667496"><desc class="bar-desc">Canada, 2018: 108 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="211.72025278840817" width="36" height="181.84998021667496"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Canada</text><text class="value-label" x="18" y="205.72025278840817" visibility="visible">108</text></g><g class="bar-group is-highlighted highlight-3" data-id="GBR" transform="translate(901, 0)"><rect class="bar" x="6" y="203.89300270813143" width="24" height="189.6772302969517"><desc class="bar-desc">United Kingdom, 2018: 113 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="203.89300270813143" width="36" height="189.6772302969517"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">United Kingdom</text><text class="value-label" x="18" y="197.89300270813143" visibility="visible">113</text></g><g class="bar-group" data-id="ESP" transform="translate(937, 0)"><rect class="bar" x="6" y="202.27168335764037" width="24" height="191.29854964744277"><desc class="bar-desc">Spain, 2018: 114 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="202.27168335764037" width="36" height="191.29854964744277"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Spain</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="BEL" transform="translate(973, 0)"><rect class="bar" x="6" y="191.19524345177842" width="24" height="202.37498955330472"><desc class="bar-desc">Belgium, 2018: 120 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="191.19524345177842" width="36" height="202.37498955330472"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Belgium</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="FRA" transform="translate(1009, 0)"><rect class="bar" x="6" y="188.43352448768567" width="24" height="205.13670851739747"><desc class="bar-desc">France, 2018: 122 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="188.43352448768567" width="36" height="205.13670851739747"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">France</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group is-highlighted highlight-6" data-id="USA" transform="translate(1045, 0)"><rect class="bar" x="6" y="164.29027863949594" width="24" height="229.2799543655872"><desc class="bar-desc">United States, 2018: 136 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="164.29027863949594" width="36" height="229.2799543655872"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">United States</text><text class="value-label" x="18" y="158.29027863949594" visibility="visible">136</text></g><g class="bar-group" data-id="PRT" transform="translate(1081, 0)"><rect class="bar" x="6" y="160.0192813533806" width="24" height="233.55095165170255"><desc class="bar-desc">Portugal, 2018: 139 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="160.0192813533806" width="36" height="233.55095165170255"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Portugal</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group" data-id="ITA" transform="translate(1117, 0)"><rect class="bar" x="6" y="146.1026769657426" width="24" height="247.46755603934054"><desc class="bar-desc">Italy, 2018: 147 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="146.1026769657426" width="36" height="247.46755603934054"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Italy</text><text class="value-label" visibility="hidden"></text></g><g class="bar-group is-highlighted highlight-4" data-id="GRC" transform="translate(1153, 0)"><rect class="bar" x="6" y="69.37304999578282" width="24" height="324.1971830093003"><desc class="bar-desc">Greece, 2018: 193 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="69.37304999578282" width="36" height="324.1971830093003"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Greece</text><text class="value-label" x="18" y="63.37304999578282" visibility="visible">193</text></g><g class="bar-group" data-id="JPN" transform="translate(1189, 0)"><rect class="bar" x="6" y="0" width="24" height="393.57023300508314"><desc class="bar-desc">Japan, 2017: 234 % of GDP</desc></rect><rect class="bar-hover-helper" x="0" y="0" width="36" height="393.57023300508314"></rect><text class="location" x="20.5" y="423.57023300508314" transform="rotate(-45 20.5 423.57023300508314)" style="display: block;">Japan</text><text class="value-label" visibility="hidden"></text></g></g></svg></div>
    <footer class="embedded-chart-footer" id="embedded-chart-footer">
        <div class="copyright-tooltip info-tooltip" tabindex="0">
            <i class="icon-ddp-copyright"></i>
            <p class="info-tooltip-content">
                © OECD
                <span class="separator">·</span>
                <a href="https://www.oecd.org/termsandconditions/" target="_top">Terms &amp; Conditions</a>
            </p>
        </div>
        <p class="explore">Compare countries on <a href="https://data.oecd.org/gga/general-government-debt.htm" target="_top" class="chart-open-referrer">data.oecd.org</a></p>
        <p class="logo"><a href="https://data.oecd.org/gga/general-government-debt.htm" target="_top" title="OECD Data" class="chart-open-referrer">OECD Data</a></p>
    </footer>
</div>
</div>
<script src="./General government debt, Total, % of GDP, 2018 or latest available_files/ddp-chart-config.js.download"></script>
<script src="./General government debt, Total, % of GDP, 2018 or latest available_files/jquery.min.js.download"></script>
<script src="./General government debt, Total, % of GDP, 2018 or latest available_files/application.js.download"></script>


<div>
    <div id="twoseven-ext-tab-media-modal" class="twoseven-ext-tab-media-modal" style="display: none;">
      <!-- Modal content -->
      <div class="twoseven-ext-tab-media-modal-content">
        <div class="iframe-container" style="height: 100%; width: 100%;">
          <span class="close">×</span>
        </div>
      </div>
    </div></div><script type="text/javascript" id="">"gtm.dom"==google_tag_manager["GTM-P5JSM4P"].macro(3)?(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"pageview"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"pageview"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"pageview"})):"customEvent"==google_tag_manager["GTM-P5JSM4P"].macro(4)?(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"customEvent"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"customEvent"}),
dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"customEvent"})):"gtm.scrollDepth"==google_tag_manager["GTM-P5JSM4P"].macro(5)?(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"gtmScrollDepth"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmScrollDepth"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"gtmScrollDepth"})):"gtm.video"==google_tag_manager["GTM-P5JSM4P"].macro(6)?0==google_tag_manager["GTM-P5JSM4P"].macro(7)?(dataLayer.push({event:"globalProperty",
UA:"UA-136634323-1",eventType:"gtmVideoStarted"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmVideoStarted"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"gtmVideoStarted"})):100==google_tag_manager["GTM-P5JSM4P"].macro(8)&&(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"gtmVideoCompleted"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmVideoCompleted"}),dataLayer.push({event:"multiAccounts",
UA:"undefined",eventType:"gtmVideoCompleted"})):"gtm.linkClick"==google_tag_manager["GTM-P5JSM4P"].macro(9)&&("undefined"!==google_tag_manager["GTM-P5JSM4P"].macro(10)?(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"gtmCTA"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmCTA"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"gtmCTA"})):"internal"==google_tag_manager["GTM-P5JSM4P"].macro(12)?(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"gtmCrossSiteLink"}),
dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmCrossSiteLink"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"gtmCrossSiteLink"})):"external"==google_tag_manager["GTM-P5JSM4P"].macro(14)&&(dataLayer.push({event:"globalProperty",UA:"UA-136634323-1",eventType:"gtmOutboundClick"}),dataLayer.push({event:"specificProperties",UA:"UA-136634323-3",eventType:"gtmOutboundClick"}),dataLayer.push({event:"multiAccounts",UA:"undefined",eventType:"gtmOutboundClick"})));</script>
<script type="text/javascript" id="">var _qevents=_qevents||[];(function(){var a=document.createElement("script");a.src=("https:"==document.location.protocol?"https://secure":"http://edge")+".quantserve.com/quant.js";a.async=!0;a.type="text/javascript";var b=document.getElementsByTagName("script")[0];b.parentNode.insertBefore(a,b)})();_qevents.push({qacct:"p-_nxutvWrg0NE8"});</script>

<noscript>
<div style="display:none;">
<img src="//pixel.quantserve.com/pixel/p-_nxutvWrg0NE8.gif" border="0" height="1" width="1" alt="Quantcast">
</div>
</noscript>
</body></html>