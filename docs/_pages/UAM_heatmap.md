---
permalink: /projects/UAM-heatmap/
author_profile: true
layout: none
---

<!-- <head>
    <script type="text/javascript">
    (function(c,l,a,r,i,t,y){
        c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
        t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
        y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
    })(window, document, "clarity", "script", "juu207ej74");
    </script>
</head> -->

<!-- <iframe src="{{ './assets/html/grid_search_test4_1_multiple_variables_add_cutoff_filter.html' | relative_url }}" width="100%" height="1000px" frameborder="0"></iframe> -->


<head>
  <script type="text/javascript">
  (function(c,l,a,r,i,t,y){
      c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
      t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
      y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
  })(window, document, "clarity", "script", "juu207ej74");
  </script>

  <style>
    .embed-2x1 {
      width: 100%;
      aspect-ratio: 2 / 1; /* width : height = 2 : 1 */
      position: relative;
      margin: 0 0 24px 0;
    }
    .embed-2x1 iframe {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      border: 0;
    }

    /* Fallback for older browsers without aspect-ratio support */
    @supports not (aspect-ratio: 1 / 1) {
      .embed-2x1 { height: auto; padding-top: 50%; } /* 1 / 2 = 50% */
      .embed-2x1 iframe { position: absolute; top: 0; left: 0; }
    }
  </style>
</head>

<!-- PDF (placed before the HTML iframe) -->
<div class="embed-2x1">
  <iframe
    src="{{ '/assets/pdf/2025_AIAA_UAM_DIS_Chicago.pdf' | relative_url }}#view=FitH"
    loading="lazy">
  </iframe>
</div>

<iframe src="{{ './assets/html/agg_siting_heatmap.html' | relative_url }}" width="100%" height="1000px" frameborder="0"></iframe>
