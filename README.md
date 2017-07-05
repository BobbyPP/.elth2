\documentclass{article}

\usepackage{graphicx}
\usepackage{xcolor}
\usepackage[margin=0.5in]{geometry}
\usepackage[utf8]{inputenc}
\usepackage{float}

\definecolor{grey}{rgb}{0.8,0.8,0.8}

\begin{document}

\begin{titlepage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}}
	\line (4,0){300} \\
	[4mm]
	\huge{\bfseries{TEMA 2 - Camp}} \\
	\line (4,0){200} \\
	[9cm]
	\large{\bfseries{Autor:}} \\
	[-2mm]
	\textcolor{grey}{\line (1,0){100}} \\
	[1mm]
	\bfseries{Nume: Politic Andrei - Bogdan} \\
	\bfseries{Anul I; Grupa 315CD} \\
	\bfseries{Universitatea Politehnica Bucuresti} \\
	\bfseries{Facultatea de Automatica si Calculatoare} \\
	\bfseries{Profil: CTI}
	\end{center}
\end{titlepage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{CUPRINS}}
	\end{center}
	\bfseries{\ }\\
	[1cm]
	\Large{EXERCITIUL 1 - Reprezentarea campurilor scalare .................................. 3} \\
	[5mm]
	\Large{EXERCITIUL 1 - COD OCTAVE .............................................................. 5} \\
	[5mm]
	\Large{EXERCITIUL 2.a. - Reprezentarea campurilor vectoriale .............................. 6} \\
	[5mm]
	\Large{EXERCITIUL 2.b. - Reprezentarea gradientului campului scalar f ...................... 8} \\
	[5mm]
	\Large{EXERCITIUL 2.c. - Reprezentarea divergentei campului vectorial G .................... 9} \\
	[5mm]
	\Large{Exercitiul 2.d. - Reprezentarea rotorului campului vectorial G ...................... 12}\\
	[5mm]
	\Large{EXERCITIUL BONUS 1 .................................................................. 16}\\
	[5mm]
	\Large{EXERCITIUL BONUS 1 .................................................................. 23}\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITIUL 1}} \\
	\huge{\bfseries{Reprezentarea campurilor scalare}} \\
	[3cm]
	\end{center}

	\bfseries{\qquad\quad Fie functia de doua variabile, f : [0,$\pi$] $\times$ [0,2$\pi$] $\rightarrow$ R,  f(x, y) = (sin(x) + sin(y))$^2$. Vom reprezenta} \\
	\bfseries{\qquad tridimensional graficul functiei pentru domeniul dat, si de asemenea curbele de nivel ale graficului in format bidimensional si tridimensional.} \\

	\begin{figure}[h]
		\includegraphics[width=180mm]{ex11.png}
		\caption{Graficul functiei si curbele de nivel (1)\label{overflow}}
	\end{figure}
	
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400}
	\end{center}
	\bfseries{\qquad \quad Graficul, privit din alt unghi:} \\
	[5mm]
	\begin{figure}[h]
		\includegraphics[width=200mm]{ex12.png}
		\caption{Graficul functiei si curbele de nivel (2)\label{overflow}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL 1 - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]
	\bfseries{function scalar\_field\_representation ()}
  
		  x = linspace(0,pi,21);\\
		  y = linspace(0,2*pi,41);\\

		  [X Y] = meshgrid(x, y);\\
		  
		  Z = (sin(X) + sin(Y)).\^ 2;\\
		  
		  figure; hold;\\
		  colormap("default");\\
		  title(sprintf("Reprezentari, ex1"));\\

		  subplot(2,2,1);\\
		    title(sprintf("Graficul functiei f(x,y) :"));\\
		    mesh(X,Y,Z);\\
		    xlabel(sprintf("x",'default'));\\
		    ylabel(sprintf("y"));\\
		    zlabel(sprintf("f(x, y)"));\\
		    shading interp;\\
		    colorbar("SouthOutSide");\\
		  subplot(2,2,2);\\
		    title(sprintf("Curbe de nivel (vizualizare 3-D) :"));\\
		    contour3(Z);\\
		    xlabel(sprintf("x"));\\
		    ylabel(sprintf("y"));\\
		    zlabel(sprintf("f(x, y)"));\\
		    colorbar("EastOutSide");\\
		  subplot(2,2,3);\\
		    title(sprintf("Curbe de nivel (vizualizare 2-D) :"));\
		    contourf(Z);\\
		    xlabel(sprintf("x"));\\
		    ylabel(sprintf("y"));\\
		    colorbar("EastOutSide");\\
		  
		endfunction\\
	
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITIUL 2}} \\
	\huge{\bfseries{Reprezentarea campurilor vectoriale}} \\
	[3cm]
	\end{center}

	\bfseries{\qquad\quad Consideram functia vectoriala depinzand de doua variabile scalare, reale (x,y): G : [-10, 10] $\times$ [-10, 10] $\rightarrow$ $R^2$,  G(x,y) = $G_x$(x,y) $\cdot$ \textbf{i} + $G_y$(x,y) $\cdot$ \textbf{j} = 2xcos(y) $\cdot$ \textbf{i} + 3ysin(x) $\cdot$ \textbf{j} . Vom reprezenta spectrul (discret al) campului G, suprapus peste harta de valori a modulelor vectorilor ce alcatuiesc spectrul.}
	\begin{figure}[h]
		\includegraphics[width = 200mm]{uu.png}
		\caption{\bfseries{Spectrul campului G (reprezentat cu albastru), suprapus peste harta de valori a modulului campului}\label{overflow}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL 2.a. - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function vectorial\_field\_representation ()}
  
		  x = linspace(-10, 10, 21);\\
		  y = linspace(-10, 10, 21);\\
		  surfx = linspace(0, 25, 26);\\
		  surfy = linspace(-5, 25, 31);\\
		  
		  [X Y] = meshgrid(x, y);\\
		  \bfseries{[surfX surfY] = meshgrid(surfx, surfy);}\\
		  figure; hold; colormap("cubehelix");\\
		  Gmodule = sqrt( (2 * (surfX-11).* cos(surfY-11)).\^2 + (3 * (surfY-11).* sin(surfX-11)).\^2);\\
		  surf(surfX, surfY, Gmodule - 50);\\
		  shading interp;\\
		  G = quiver(2 * X.* cos(Y), 3 * Y.* sin(X));\\
		  
		  colorbar("EastOutSide");\\
		  
		endfunction\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\bfseries{\qquad\quad In continuare, va fi prezentat graficul gradientului campului scalar $f$ ($f$ de la Exercitiul 1), suprapus peste reprezentarea curbelor de nivel (echivalorilor) graficului lui $f$.} \\
	\bfseries{.\qquad\quad Pe caz general, gradientul unei functii de variabila multipla este un vector ce contine derivatele partiale ale variabilei si care, in sens fizic, indica panta cu gradul cel mai mare de inclinare de pe graficul functiei, in sensul de urcare, intr-un punct anume. In cazul campului scalar reprezentat de valorile functiei f, gradientul apare sub forma vectorului [ $\partial$f / $\partial$x, $\partial$f / $\partial$y ], adica este egal cu [ $\partial$( $(sin(x) + sin(y))^2$ ) / $\partial$x, $\partial$( $(sin(x) + sin(y))^2$ ) / $\partial$y ]. Se obtine ca gradientul campului scalar $f$ intr-un punct de coordonate (x, y) este [ 2 $\cdot$ (sin(x) + sin(y)) $\cdot$ cos(x), 2 $\cdot$ (sin(x) + sin(y)) $\cdot$ cos(y) ] .} \\
	[5mm]
	\begin{figure}[h]
		\includegraphics[width = 200mm]{grad_f_nivel.png}
		\caption{\bfseries{Gradientul campului scalar $f$ si echivalorile graficului lui $f$.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL 2.b. - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function gradient\_f ()}
  
		  x = linspace(0,pi,21);\\
		  y = linspace(0,2*pi,41);\\
		  
		  [X Y] = meshgrid(x, y);\\
		  
		  function\_f = (sin(X) + sin(Y)).\^2;\\
		  derx = 2 * (sin(X) + sin(Y)).* cos(X);\\
		  dery = 2 * (sin(X) + sin(Y)).* cos(Y);\\
		  
		  figure; hold;\\
		  colormap("cubehelix");\\

		  title(sprintf("Campul vectorial generat de gradientul functiei f, suprapus peste curbele de nivel ale acesteia :"));\\
		  quiver(derx, dery);\\
		  contourf(function\_f);\\
		  colorbar("EastOutSide");\\
		  
		endfunction\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\bfseries{\qquad\quad Vom calcula si vom reprezenta divergenta campului vectorial \textbf{G}. Pe caz general, divergenta reprezinta densitatea de flux dintr-o unitate infinit de mica de volum, specifica unui punct. Matematic, considerand un camp vectorial \textbf{G}, cu G(x,y) = $G_x$(x,y) $\cdot$ \textbf{i} + $G_y$(x,y) $\cdot$ \textbf{j}, divergenta acestuia este $\partial$G$_x$(x,y) / $\partial$x + $\partial$G$_x$(x,y) / $\partial$y .} \\
	\bfseries{.\qquad\quad In cazul nostru, divergenta lui \textbf{G} este $2$ $\cdot$ $cos(x)$ + $3$ $\cdot$ $sin(y)$ .} \\
	[5mm]
	\begin{figure}[h]
		\includegraphics[width = 200mm]{oooOooOo.png}
		\caption{\bfseries{Divergenta campului vectorial \textbf{G} (bidimensional).}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 200mm]{asdama.png}
		\caption{\bfseries{Divergenta campului vectorial \textbf{G} (tridimensional).}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL 2.c. - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function divergence\_G ()}
		  
		  x = linspace(-10, 10, 21);\\
		  y = linspace(-10, 10, 21);\\
		  
		  [X Y] = meshgrid(x, y);\\
		  
		  figure; hold; colormap("ocean");\\
		  title("Reprezentarea grafica a divergentei campului vectorial G :");\\
		  \%G = quiver(2 * X.* cos(Y), 3 * Y.* sin(X)); ------------------------- campul vectorial G\\
		  divergence\_G = 2 * cos(Y) + 3 * sin(X);\\
		  mesh(divergence\_G);\\
		  shading interp;\\
		  colorbar("EastOutSide");\\
		  
		endfunction\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\bfseries{\qquad\quad In continuare vom calcula rotorul campului vectorial \textbf{G}. In sens fizic, rotorul indica rotatia unui vector din camp, in jurul punctului din domeniu de care apartine. Vectorul rotorului este orientat dupa regula burghiului. Sensul orientarii rotorului (perpendicular pe suprafata campului) indica sensul de rotatie al vectorului, iar modulul acestuia descrie viteza de rotatie a vectorului din camp. Matematic, pentru un camp vectorial bidimensional G(x,y) = $G_x$(x,y) $\cdot$ \textbf{i} + $G_y$(x,y) $\cdot$ \textbf{j}, rotorul este egal cu: $\partial$G$_y$(x,y) / $\partial$x - $\partial$G$_x$(x,y) / $\partial$y .} \\
	[1cm]
	\begin{figure}[h]
		\includegraphics[width = 200mm]{curll.png}
		\caption{\bfseries{Rotorul campului vectorial \textbf{G} (bidimensional).}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 200mm]{curlll.png}
		\caption{\bfseries{Rotorul campului vectorial \textbf{G} (tridimensional).}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL 2.d. - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function curl\_G ()}

		  x = linspace(-10, 10, 21);\\
		  y = linspace(-10, 10, 21);\\
		  
		  [X Y] = meshgrid(x, y);\\
		  
		  figure; hold; colormap("ocean");\\
		  title("Reprezentarea grafica a rotorului campului vectorial G :");\\
		  \%G = quiver(2 * X.* cos(Y), 3 * Y.* sin(X),'r'); ------------------------- campul vectorial G\\
		  curl\_G = 3 * Y.* cos(X) + 2 * X.* sin(Y);\\
		  mesh(curl\_G);	--pentru a doua figura am folosit contour\\
		  quiver(-2 * X.* sin(Y), 3 * Y.* cos(X), 'r');\\
		  \%contourf(curl\_G);	--pentru prima figura am folosit mesh\\
		  shading interp;\\
		  colorbar("EastOutSide");\\
		  
		endfunction
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITII BONUS}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITIUL 1}}\\
	\huge{\bfseries{Reprezentarea campurilor scalare variabile in timp}} \\
	[3cm]
	\end{center}

	\bfseries{\qquad\quad Consideram o functie reala de 3 variabile scalare (2 variabile spatiale x si y si o variabila temporala t) $f$(x,y,t), unde x si y reprezinta coordonate carteziene, iar t reprezinta timpul.}\\
	\bfseries{\qquad\quad Fie aceasta functie $f$ : [0, $\pi$] $\times$ [0, 2$\pi$] $\times$ \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10\} $\rightarrow$ R, $f$(x,y,t) = x $\cdot$ sin(y - t $\cdot$ 0.1) $\cdot$ i + 3 $\cdot$ y $\cdot$ cos(x + t $\cdot$ 0.1) $\cdot$ j. Vom realiza o animatie a hartilor echivalorilor functiei, in intervalul de timp pe care este definita functia. Variabila temporala putand lua 10 valori, inseamna ca animatia va cuprinde 10 grafice pe care le vom reprezenta mai jos.}\\

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig11.png}
		\caption{\bfseries{Animatia 1.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig12.png}
		\caption{\bfseries{Animatia 2.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig13.png}
		\caption{\bfseries{Animatia 3.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig14.png}
		\caption{\bfseries{Animatia 4.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig15.png}
		\caption{\bfseries{Animatia 5.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig16.png}
		\caption{\bfseries{Animatia 6.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig17.png}
		\caption{\bfseries{Animatia 7.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig18.png}
		\caption{\bfseries{Animatia 8.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig19.png}
		\caption{\bfseries{Animatia 9.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig20.png}
		\caption{\bfseries{Animatia 10.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL BONUS 1 - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function animated\_plot ()}
  
		  graphics\_toolkit("gnuplot");\\
		  x = linspace(0,pi,6);\\
		  y = linspace(0,2*pi,11);\\
		  t = linspace(1,10,10);\\
		  \bfseries{[X Y] = meshgrid(x, y);}\\
		  
		  for i = 1 : 10\\
		    figure;\\
		    Z = (cos(X - t(i)*0.1) + cos(Y + t(i)*0.1)).\^2;\\
		    
		    colormap("default");\\
		    title(sprintf("Reprezentari, ex1"));\\
		    contourf(Z);\\
		    Fname = sprintf("file\_\%i.png", 1, ";;");\\
		    print(Fname);\\
		    colorbar("SouthOutSide");\\
		  endfor\\
		  
		endfunction\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITII BONUS}} \\
	\line (1,0){400} \\
	\Huge{\bfseries{EXERCITIUL 2}}\\
	\huge{\bfseries{Reprezentarea campurilor vectoriale variabile in timp}} \\
	[3cm]
	\end{center}

	\bfseries{\qquad\quad Consideram o functie vectoriala de 3 variabile scalare (2 variabile spatiale x si y si o variabila temporala t) $f$(x,y,t), unde x si y reprezinta coordonate carteziene, iar t reprezinta timpul.}\\
	\bfseries{\qquad\quad Fie aceasta functie $f$ : [0, $\pi$] $\times$ [0, 2$\pi$] $\times$ \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10\} $\rightarrow$ R, $f$(x,y,t) = x $\cdot$ sin(y - t $\cdot$ 0.3) $\cdot$ i + 3 $\cdot$ y $\cdot$ cos(x + t $\cdot$ 0.3) $\cdot$ j. Vom realiza o animatie a spectrului campului functiei, in intervalul de timp pe care este definita functia. Variabila temporala putand lua 10 valori, inseamna ca animatia va cuprinde 10 grafice pe care le vom reprezenta mai jos.}\\

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig31.png}
		\caption{\bfseries{Animatia 1.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig32.png}
		\caption{\bfseries{Animatia 2.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig33.png}
		\caption{\bfseries{Animatia 3.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig34.png}
		\caption{\bfseries{Animatia 4.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig35.png}
		\caption{\bfseries{Animatia 5.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig36.png}
		\caption{\bfseries{Animatia 6.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig37.png}
		\caption{\bfseries{Animatia 7.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig38.png}
		\caption{\bfseries{Animatia 8.}}
	\end{figure}
	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig39.png}
		\caption{\bfseries{Animatia 9.}}
	\end{figure}
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\end{center}

	\begin{figure}[h]
		\includegraphics[width = 100mm]{fig40.png}
		\caption{\bfseries{Animatia 10.}}
	\end{figure}

\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	\huge{\bfseries{EXERCITIUL BONUS 2 - COD OCTAVE}}
	\end{center}
	\bfseries{\ }\\
	[1cm]

	\bfseries{function animated\_plot\_for\_spectrum ()}

		graphics\_toolkit("gnuplot");\\
		  x = linspace(0,pi,6);\\
		  y = linspace(0,2*pi,11);\\
		  t = linspace(1,10,10);\\
		  \bfseries{[X Y] = meshgrid(x, y);}\\
		  for i = 1 : 10\\
		    figure; hold;\\
		    colormap("default");\\
		    title(sprintf("Reprezentari, ex1"));\\
		    contourf(X);\\
		    G = quiver(X.* sin(Y - t(i)*0.3), 3 * Y.* cos(X + t(i)*0.3), 'b');\\
		    Fname = sprintf("file\_\%i.png", i, ";;");
		    print(Fname);\\
		  endfor\\
		  
		endfunction\\
\end{newpage}
\begin{newpage}
	\begin{center}
	\textcolor{grey}{\bfseries{B A Z E L E \qquad E L E C T R O T E H N I C I I}} \\
	\line (1,0){400} \\
	[1cm]
	\Huge{\bfseries{REFERINTE}}\\
	[3cm]
	\end{center}
	
	

\end{newpage}
\end{document}
