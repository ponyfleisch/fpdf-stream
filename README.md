fpdf-stream
===========

This is a modified version of fpdf (1.7) which outputs pdf generation directly to the browser as it is generated page by page.

Still pre-alpha.

Usage
=====

    header('Content-Type: application/pdf');
    header('Content-Disposition: inline; filename="schnitzel.pdf"');


    $pdf = new Pdf();

    $pdf->startOutput();

    for($i=0; $i < $pages; $i++){
        $pdf->AddPage();
        ob_flush();
        $pdf->SetFont('Arial','B',16);
        for($j=0; $j < 500; $j++){
            $pdf->Cell(10, 10,'Hello World! '.$j);
        }
    }

    $pdf->endOutput();
