## PDFMerger for PHP (PHP 5 & 7 Compatible)

Original written by http://pdfmerger.codeplex.com/team/view<br />
Forked from https://github.com/myokyawhtun/PDFMerger
and from https://github.com/clegginabox/pdf-merger

I've just forked this package to apply the latest patches,
especially the one from aaronbauman to ignore FPDI exception 
so that our merge can continue even with errors.

## Composer Compatible

To install add this line to your composer.json

```"attilafabian/pdf-merger": "dev-master"```

or

```composer require attilafabian/pdf-merger:dev-master```

### Example Usage
```php

$pdf = new \FBO\PDFMerger\PDFMerger;

$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4');
$pdf->addPDF('samplepdfs/two.jpg');
$pdf->addPDF('samplepdfs/three.pdf', 'all');

//You can optionally specify a different orientation for each PDF
$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4', 'L');
$pdf->addPDF('samplepdfs/two.pdf', '1-2', 'P');

$pdf->merge('file', 'samplepdfs/TEST2.pdf', 'P');

// REPLACE 'file' WITH 'browser', 'download', 'string', or 'file' for output options
// Last parameter is for orientation (P for protrait, L for Landscape). 
// This will be used for every PDF that doesn't have an orientation specified
```
