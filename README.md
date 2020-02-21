# Ranger-Mish-ImageWoof-5

see the [original repo](https://github.com/lessw2020/Ranger-Mish-ImageWoof-5)

# ResNet with a Twist

* been testing mostly on imagewoof, size=128, epoch=5 (at 68ish, not even close to the current Leaderboard)

* had 2 runs on imagewoof, size=128, epoch=80 (both broke current best of 87.20)

```
python3 train.py --run 1 --woof 1 --size 128 --bs 64 --mixup 0 --epoch 80 --lr 3e-3 --gpu 2 --opt ranger --mom .95 --sched_type flat_and_anneal --ann_start 0.72 --sa 1
Mish activation loaded...
/home/hebe/.fastai/data/imagewoof2
8121  annealing start
epoch     train_loss  valid_loss  accuracy  top_k_accuracy  time    
0         2.022503    2.374396    0.271825  0.789005        00:43       
1         1.727930    1.583410    0.521761  0.921863        00:40       
2         1.584959    1.577423    0.525325  0.923899        00:39       
3         1.479036    1.521124    0.575464  0.939934        00:39       
4         1.393512    1.655825    0.556376  0.926444        00:39       
5         1.313412    1.265099    0.676253  0.953423        00:39       
6         1.259269    1.254370    0.686180  0.955714        00:39       
7         1.195757    1.194301    0.713413  0.967931        00:39       
8         1.144299    1.216587    0.702469  0.955459        00:39       
9         1.104744    1.080966    0.763808  0.972003        00:40        
10        1.066096    1.118122    0.755409  0.967422        00:40        
11        1.030882    1.074099    0.767625  0.971749        00:39        
12        1.007180    1.079892    0.768134  0.969967        00:39        
13        0.990480    1.043782    0.782133  0.976075        00:39        
14        0.950845    1.076493    0.770680  0.973021        00:36        
15        0.931778    1.020714    0.790786  0.975566        00:36        
16        0.912669    1.039503    0.784933  0.974548        00:34        
17        0.891832    0.971171    0.809875  0.982438        00:37        
18        0.870686    1.038600    0.790532  0.976839        00:35        
19        0.851990    0.968615    0.815729  0.979639        00:38        
20        0.830882    0.958012    0.813693  0.978366        00:37        
21        0.820493    0.947207    0.827946  0.978366        00:37        
22        0.811189    1.013733    0.789259  0.973785        00:36        
23        0.796587    0.932968    0.824637  0.981929        00:35        
24        0.772534    0.959153    0.807076  0.980911        00:32        
25        0.758081    0.969609    0.813948  0.976584        00:32        
26        0.757106    0.985923    0.809621  0.976584        00:32        
27        0.750355    0.949914    0.818529  0.979639        00:32        
28        0.724022    0.975528    0.810639  0.973021        00:32        
29        0.721202    0.926338    0.833545  0.980402        00:32        
30        0.729917    0.955257    0.817765  0.980402        00:32        
31        0.712929    0.947147    0.820820  0.974294        00:31        
32        0.694554    0.947516    0.822601  0.975312        00:31        
33        0.689622    0.919614    0.835073  0.980911        00:32        
34        0.692636    0.967377    0.819547  0.974294        00:31        
35        0.668777    0.936643    0.828710  0.976584        00:32        
36        0.666183    0.951694    0.824128  0.975821        00:31        
37        0.665233    0.937091    0.828201  0.979130        00:32        
38        0.665244    0.972759    0.813948  0.977857        00:32        
39        0.663719    0.916069    0.840926  0.978621        00:31        
40        0.653832    0.940514    0.826164  0.974039        00:32        
41        0.646085    0.911459    0.839145  0.980657        00:31        
42        0.648014    0.936493    0.830237  0.977857        00:32        
43        0.639409    0.915711    0.838127  0.974294        00:32        
44        0.633600    0.946104    0.823619  0.972512        00:32        
45        0.635634    0.915517    0.838636  0.980148        00:33        
46        0.637270    0.941750    0.827691  0.978621        00:31        
47        0.628677    0.940204    0.828455  0.972767        00:32        
48        0.632348    0.979761    0.812675  0.973276        00:31        
49        0.627588    0.947120    0.825401  0.975057        00:32        
50        0.630593    0.928716    0.826419  0.979893        00:31        
51        0.622845    0.922130    0.828710  0.975312        00:32        
52        0.609950    0.966539    0.818529  0.970730        00:32        
53        0.614929    0.915125    0.839654  0.975821        00:31        
54        0.618746    0.958086    0.821074  0.975821        00:32        
55        0.603149    0.897992    0.846780  0.975057        00:31        
56        0.610972    0.964282    0.831509  0.969458        00:32        
57        0.611617    0.912939    0.842199  0.975821        00:33        
58        0.599287    0.933939    0.832782  0.974548        00:32        
59        0.598446    0.893805    0.850089  0.979130        00:32        
60        0.595965    0.932371    0.829728  0.972003        00:32        
61        0.590639    0.928514    0.834818  0.977348        00:32        
62        0.580473    0.945741    0.831509  0.975057        00:32        
63        0.586239    0.899869    0.845253  0.975566        00:31        
64        0.578509    0.907422    0.845762  0.974548        00:32        
65        0.571817    0.889337    0.848817  0.977348        00:31        
66        0.555313    0.895356    0.853652  0.980148        00:32        
67        0.555615    0.888323    0.851871  0.975312        00:32        
68        0.550577    0.906525    0.846017  0.969203        00:32        
69        0.546040    0.864806    0.860270  0.978366        00:31        
70        0.543199    0.872252    0.854161  0.976584        00:31        
71        0.536674    0.862499    0.863069  0.975566        00:32        
72        0.530267    0.856951    0.865869  0.978875        00:32        
73        0.527796    0.847876    0.864342  0.977348        00:32        
74        0.527059    0.831127    0.871214  0.978366        00:31        
75        0.523231    0.830703    0.871469  0.977857        00:32        
76        0.521974    0.838369    0.870450  0.979639        00:31        
77        0.519366    0.834434    0.872232  0.978112        00:32        
78        0.519410    0.829522    0.874268  0.978875        00:32        
79        0.518741    0.832961    0.872741  0.978112        00:32        
[0.872741]
0.87274116
0.0
```

```
python3 train.py --run 1 --woof 1 --size 128 --bs 64 --mixup 0 --epoch 80 --lr 4e-3 --gpu 2 --opt ranger --mom .95 --sched_type flat_and_anneal --ann_start 0.72 --sa 1
Mish activation loaded...
/home/hebe/.fastai/data/imagewoof2
8121  annealing start
epoch     train_loss  valid_loss  accuracy  top_k_accuracy  time    
0         2.033727    2.158300    0.270043  0.747264        00:34       
1         1.767194    1.674001    0.468567  0.905574        00:33       
2         1.607370    1.772913    0.483584  0.889794        00:33       
3         1.479854    1.375639    0.628659  0.949351        00:37       
4         1.406474    1.506548    0.570629  0.939934        00:38       
5         1.318333    1.296703    0.660473  0.954950        00:38       
6         1.242032    1.496394    0.578264  0.937898        00:37       
7         1.190736    1.151045    0.728175  0.971240        00:37       
8         1.137544    1.207529    0.715195  0.965386        00:37       
9         1.102395    1.077394    0.761008  0.973021        00:38        
10        1.071235    1.101264    0.754645  0.974548        00:38        
11        1.043530    1.023634    0.795113  0.976330        00:38        
12        1.003704    1.067822    0.775515  0.973276        00:37        
13        0.971245    1.023261    0.786205  0.977348        00:37        
14        0.958066    1.050064    0.782387  0.974294        00:35        
15        0.950064    1.004832    0.801731  0.978112        00:38        
16        0.916014    1.028962    0.784169  0.978112        00:39        
17        0.911777    0.979879    0.805803  0.982184        00:41        
18        0.879377    1.060243    0.783151  0.976330        00:40        
19        0.861342    0.970374    0.811911  0.982438        00:42        
20        0.857277    0.973324    0.808348  0.980657        00:41        
21        0.838787    0.968409    0.809621  0.978621        00:41        
22        0.812584    1.008401    0.800204  0.980657        00:42        
23        0.805707    0.939784    0.823110  0.980911        00:41        
24        0.799035    0.969676    0.813948  0.977348        00:41        
25        0.787906    0.937383    0.826928  0.981420        00:41        
26        0.770508    1.012067    0.803767  0.976075        00:41        
27        0.766696    0.915676    0.836854  0.978621        00:41        
28        0.755386    1.015051    0.798422  0.974039        00:41        
29        0.737409    0.939851    0.831255  0.980911        00:42        
30        0.738328    0.955008    0.824637  0.977857        00:41        
31        0.728349    0.929819    0.834054  0.981929        00:41        
32        0.716177    0.938203    0.828964  0.979130        00:41        
33        0.710949    0.925545    0.837363  0.977348        00:41        
34        0.698417    0.949825    0.826164  0.973785        00:41        
35        0.697600    0.908815    0.846526  0.981166        00:41        
36        0.686996    0.961832    0.818020  0.976839        00:41        
37        0.675849    0.919532    0.833036  0.981675        00:42        
38        0.670214    0.934102    0.835836  0.978366        00:41        
39        0.680636    0.938526    0.830237  0.978112        00:41        
40        0.665111    0.949361    0.815475  0.976584        00:41        
41        0.651326    0.930171    0.834563  0.981166        00:41        
42        0.664673    0.996088    0.808348  0.970730        00:38        
43        0.652037    0.926417    0.833036  0.981166        00:36        
44        0.651367    0.953700    0.826419  0.978875        00:37        
45        0.655912    0.910768    0.838636  0.978366        00:37        
46        0.649673    0.928072    0.836854  0.976330        00:38        
47        0.637211    0.925231    0.835327  0.977093        00:37        
48        0.648310    0.917233    0.835073  0.979639        00:38        
49        0.626146    0.907653    0.848307  0.977093        00:37        
50        0.639686    0.938930    0.835836  0.976330        00:38        
51        0.636308    0.930569    0.831764  0.977348        00:38        
52        0.621369    0.932276    0.835073  0.977348        00:39        
53        0.620125    0.929120    0.836854  0.979384        00:38        
54        0.616540    0.960319    0.828964  0.976839        00:36        
55        0.633396    0.918848    0.836600  0.976584        00:38        
56        0.609307    0.942272    0.827946  0.974294        00:40        
57        0.613859    0.932377    0.834563  0.977857        00:41        
58        0.609284    0.924755    0.846780  0.971749        00:41        
59        0.604903    0.900164    0.848562  0.976584        00:42        
60        0.604353    0.956656    0.826419  0.976584        00:41        
61        0.603087    0.906927    0.840926  0.978366        00:42        
62        0.589010    0.915006    0.843981  0.973530        00:40        
63        0.587387    0.892191    0.848307  0.978621        00:42        
64        0.581103    0.892770    0.850598  0.976075        00:41        
65        0.575651    0.903179    0.844490  0.980148        00:41        
66        0.567173    0.886469    0.855179  0.979130        00:40        
67        0.563621    0.886168    0.851362  0.975821        00:37        
68        0.548623    0.874184    0.860270  0.975566        00:37        
69        0.551961    0.869802    0.862560  0.976075        00:45        
70        0.540013    0.885547    0.854670  0.977857        00:45        
71        0.533919    0.856328    0.868160  0.975057        00:45        
72        0.534668    0.851290    0.871469  0.979130        00:47        
73        0.529437    0.843904    0.868923  0.977093        00:45        
74        0.528932    0.847306    0.869941  0.978366        00:46        
75        0.528881    0.841938    0.866887  0.979384        00:45        
76        0.525612    0.837583    0.869687  0.977093        00:47        
77        0.519637    0.835700    0.870450  0.978112        00:45        
78        0.520722    0.836971    0.872741  0.977857        00:46        
79        0.523173    0.833335    0.873250  0.977602        00:45        
[0.87325]
0.8732502
0.0
```


A quick summary of the underlying mathematics:

ResNet | "heat" equation
:----:|:-------:
input layer | initial condition
feed forward | solving the equation
hidden layers | solution at intermediate times
output layer | solution at final time
convolution with 3×3 kernel | differential operator of order ≤ 2
weights | coefficients
boundary handling (padding) | boundary condition
multiple channels/filters/feature_maps | system of (coupled) PDEs
e.g. 16×16×3×3 kernel | 16×16 matrix of differential operators
16×16×1×1 kernel | 16×16 matrix of constants
groups=2 (in Conv2d) | matrix is block diagonal (direct sum of 2 blocks)

The idea of **ResNet with a Twist** is to add "variable coefficients" in front of the differential operators, variables being simply "linear in the x and y direction" which suffices for rotation and scaling.
