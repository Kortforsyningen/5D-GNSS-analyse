Stepvis vejledning til at k�re programmerne: 
1. �bn Octave (evt. MatLab)
- Hovedprogrammet er TimeSeriesAnalysis.m
2. �bn hovedprogrammet og ret evt. inputfilnavne (INPUT FILENAMES:) og andre muligheder s� de passer (forklaret som kommentarer i toppen af programmet p� linje 22-31.)
- S�rg for input filerne ligger de rigtige steder if�lge hovedprogrammet. De skal ligge i mappen inputs.
- S�rg for at output filerne ligger de rigtige steder if�lge hovedprogrammet. De skal ligge i mappen outputs (def. p� linje 118-125 i TimeSeriesAnalysis).

OBS: F�lgende settings er sat til deres default v�rdier som g�r programmet virker, �ndr. kun efter behov.
- Sl� evt. andre settings til/fra ved at definere betingelser til 1 eller 0, eller conditions fra 1 til 4. Vigtige settings er:
* outputENH = 0/1 (udregn for Eastings og Northings?) linje 43.
* exclusionoption = 1:4 (v�lg fra 1 til 4, definerer hvordan og hvilke data bliver brugt, og om kun 1 station bliver udregnet eller alle). Linje 45-59.
* Waitbar (denne waitbar f�r scriptet til at k�re en anelse langsommere, s� du kan evt. override denne if-statement med DoWait = 0 hvis du gerne vil k�re programmet ekstra hurtigt. 
Tager 549 sekunder med waitbar og 319 sekunder uden, for alle stationer). Linje 62-67.
* min_points (minimum number of observations. Skal mindst v�re min_points = 2, hvilket vil sige at minimum 3 observationer bliver brugt pr. station. (min. stationer == min_points + 1). 
Hvis mindre bliver der en masse divisions by zero). Linje 76.
* do_binning (v�lger om du bruger binning eller ej (hvis observationer er mindre end 14 dage fra hinanden midles de om betragtes som et enkelt punkt) ). Linje 84 og 86 for binsze in days.
* figures // strength_figures (v�lger om du vil have styrkeplots outputtet til figures\strength folderen, eller normale figures med statistik outputtet til figures folderen. 
Du kun kun bruge en af dem, ikke begge pg.a. bug i Octave opdatering! Linje 92-93.
* pkg load statistics (loader statistics fra forge pakken, som skal installeres f�r denne linje k�res. Install kommandoen er udkommenteret p� linje 3). Linje 135.
* histcalc = 0/1 (hvis 1 udregner den og viser histogrammer, som udregnes inde i ResidualAnalysis funktionen p� linje 220-235). Linje 148.

3. K�r programmet 
  Se resultatet i mapperne: figures, output og residuals
- Andre programmer man kan rette i:
  linreg.m (funktion, som laver statistikberegningen)
  linregplot.m (plotter figurer)
  ResidualAnalysis.m

Kr�vet for at programmet kan k�re:
1. K�r kommandoen 'pkg install -forge statistics' (uden apostrofer) i octave kommandolinjen, hvis systemet
ikke allerede har det.