![[Pasted image 20241107153652.png]]
Sistem pentru reverberatie

Sample time: 16000
y\[n\]=x\[n\] + a \*y\[n-D\]

x\[n\] = delta\[n\] = {1, n=0; 0, in rest} y\[n\] = 0, n < 0

n = 0 => y\[0\]= x\[0\] + a\*y\[-1\] = 1
n = 1 => y\[1\] = x\[1\] + a \* y\[0\] = a
n = 2 => y\[2\] = x\[2\] + a \* y\[1\] = a^2
...
n = k => y\[k\] = a^k = { y\[k\] inf, k -> inf a > 0; y\[k\] -> 0; a < 0, k -> inf}

h\[n\] = a^k \* u\[n\]  => functia pondere a sistemului(functia care caracterizeaza sistemul)
u -> treapta unitate

y\[n\] = \<SIGMA de k\> h\[k\]\*x\[n-k\]


# Transformata Laplace

X\[z\] = \<SUMA de n\> x\[n\] \*z^-n
z apartine C, z = ro\*e^<sup>j*TETHA</sup>
			=|z|\*e^<sup>j*TETHA<sub>z</sub></sup>
			

Aplicand transformata Laplace pe y\[n\]=x\[n\] + a \*y\[n-D\] obtinem:
Y(z) = X(z) + a\*z^<sup>-D</sup> \* Y(z)

Y(z)/X(z) = H(z)
H(z) este trasformata lui h\[z\]

Din Y(z) = X(z) + a\*z^<sup>-D</sup> \* Y(z) Obtinem
Y(z)/X(z) = H(z) = 1/(1-a\*z^<sup>-D</sup>)
=> h\[n\] = P(z)/Q(z)
Radacinile lui Q(z) sunt poli
Radacinile lui P(z) sunt zerouri
Deci ecuatia noastra are poli: z=a

>[!WARNING]
>Un sistem este stabil daca toti polii se afla in interiorul cercului de raza unitate(|z| = 1)

