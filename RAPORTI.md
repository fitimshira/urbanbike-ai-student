# Raporti i studentit: UrbanBike AI

Studenti: Fitim Shira
Grupi (nëse punohet në grup): Grupi Nr.3
Data:
GitHub-i im:
Figma:https://www.figma.com/design/YcJqcNs2V65wSfobaeWA7n/UrbanBike-AI-%E2%80%93-Fitim-Shira?node-id=0-1&t=9LdjGAaxmQXpSFsO-1

## Qëllimi

Problemi që zgjidhim: Sa qira biçikletash priten për ditën pasuese në Washington, D.C.?
Target-i y: rentals.
Predictorët X:
Koha kur parashikojmë dhe çfarë informacioni është i njohur:

## Pastrimi

Burimet reale dhe çelësi i bashkimit:
Dallimi mes origjinaleve dhe kopjes didaktike:
Rreshtat para/pas:
Dublimet:
Mungesat para/pas konvertimit:
Arsyeja e imputimit vetëm me train:

## Grafikët

Vëzhgimi 1 dhe figura përkatëse: Figura: reports/figures/01_demand.png

Grafiku paraqet numrin e qirave ditore dhe
mesataren e shtatë ditëve të mëparshme.
Ai na ndihmon të identifikojmë ndryshimet
dhe luhatjet e kërkesës gjatë periudhës
së trajnimit.

Vëzhgimi 2 dhe figura përkatëse:Figura: reports/figures/02_workingday.png

Grafiku krahason mesataren e qirave
në ditët e punës me ditët e pushimit.
Ky krahasim ndihmon të kuptojmë nëse
lloji i ditës lidhet me kërkesën
për biçikleta.

Pse një lidhje e dukshme nuk provon shkakësi:

## Vlerësimi

| Modeli | Validation MAE | Test MAE | Test RMSE | Test R² |
|---|---:|---:|---:|---:|
| Yesterday | 916.402 | 1330.386 | 0.539 |
| DummyMean | 2494.628 | 2790.064 | -1.027 |
| Ridge | 893.251 | 1252.655 | 0.591 |
| RandomForest | 1671.499 | 2042.654 | -0.087 |

Modeli i zgjedhur nga validation dhe arsyeja:
Ridge, sepse arriti MAE më të ulët në validation
(687.558) krahasuar me RandomForest (1821.528).

Rezultati i provës me Random Forest:
RandomForest pati rezultate më të dobëta se Ridge.
Në test arriti MAE 1671.499 dhe R² -0.087.

Interpretimi i gabimit në qira për ditë:
Modeli Ridge ka MAE 893.251, që do të thotë
se gabimi absolut mesatar është rreth
893 qira biçikletash në ditë.

Rezultati i klasifikimit, nëse u realizua:
Nuk është realizuar ende. Do të plotësohet
pas ekzekutimit të skedarit 04_classify.py.


## Kufizimet

1.Projekti përdor të dhëna historike të viteve 2011–2012 vetëm për Washington, D.C.
2.Të dhënat meteorologjike të NASA-s mund të mos pasqyrojnë saktësisht motin lokal.
3.Parashikimi përdor të dhënat e ditës së mëparshme dhe nuk është testuar në kohë reale.

## Kontributet individuale

| Studenti | Skedari/ekrani | Puna dhe vendimi | Commit/prova |
|---|---|---|---|
| Fitim Shira | 01_clean.py, 02_visualize.py | Pastrimi i të dhënave dhe krijimi i grafikëve | data_quality.json, figurat |
| Fatlind Shira | 03_train.py, 04_classify.py | Trajnimi, klasifikimi dhe vlerësimi i modeleve AI | regression_metrics.csv, classification_metrics.json |
| Fitim Shira | RAPORTI.md, Figma | Dokumentimi dhe dizajni i ndërfaqes | Raporti, lidhja Figma |
| Fatlind Shira | app.py, run_all.py | Zhvillimi dhe testimi i aplikacionit | Aplikacioni funksional |

## Burimet

UCI: https://doi.org/10.24432/C5W894
NASA: https://power.larc.nasa.gov/docs/services/api/temporal/daily/
Provenienca lokale: data/raw/provenance.json
