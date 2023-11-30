---
title:  "Mitigating catastrophic interference in models of bilingual lexical acquisition (In prep)"
mathjax: true
layout: post
categories: media
---


> Marian Simarro González, Thomas Hannagan,  Nils Beck, Manuel Carreiras, James Magnuson (In prep)
>

In this project, we aimed to extend the CLS framework to the domain of acquiring lexical knowledge in two languages to avoid catastrophic interference

See the [poster] I presented in SNL 2023!

<div id="pdf-container"></div>

<script>
  // Get the PDF URL
  const pdfUrl = 'assets/cls-bilingual-poster-2023.10.17c.pdf';

  // Initialize PDF.js
  PDFJS.disableWorker = true;
  PDFJS.getDocument(pdfUrl).then(function(pdf) {
    // Get the first page
    const page = pdf.getPage(1);

    // Get the canvas element
    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');

    // Render the page to the canvas
    page.render(canvas);

    // Append the canvas to the container
    document.getElementById('pdf-container').appendChild(canvas);
  });
</script>
