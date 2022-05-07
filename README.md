# ANUALIDADES-ORDINARIAS

Anualidades ordinarias
Se pueden usar los argumentos arrears o immediate en las funciones accumulatedValue y annuity
install.packages("lifecontingencies")
library(lifecontingencies)

1. Una persona ahorra $400 cada seis meses y los invierte al 4% convertible semestralmente.  el importe de sus ahorros después de 7 años.

400 * accumulatedValue(i = 0.04 / 2, n = 7 * 2, k = 1, type = "arrears")

2. Un empleado invierte $130 al final de cada trimestre en un fondo que paga 7% convertible trimestralmente. ¿Cuál será el importe del fondo precisamente después de 12 depósitos?

    130 * accumulatedValue(i = 0.07 / 4, n = 12, m = 0, k = 1, type = "arrears")

3. ¿Cuál es el valor presente de $1600 depositados en una cuenta al final de cada trimestre durante 4 años, si la tasa de interés es del 8% convertible trimestralmente?
  
  1600 * annuity(i = 0.08 / 4, n = 4 * 4, type = "arrears") 

4. ¿Cuánto debió depositarse el 1 de junio de 2005 en un fondo que pagó el 10% convertible semestralmente con el objeto de poder hacer retiros semestrales de $2500 cada uno, desde el 1 de diciembre de 2005 hasta el 1 de diciembre de 2010?
  
  2500 * annuity(i = 0.10 / 2, n = 1 + 5 * 2, type = "immediate")

5. Una persona compra un coche nuevo en $14000, si entrega su coche usado valorado en $4250 como parte de pago, ¿cuánto tendrá que pagar en efectivo el día de hoy si el saldo restante se lo liquidará mediante el pago de $550 al final de cada mes durante 18 meses, con intereses al 6% convertible mensualmente?
  
  14000 - 4250 - 550 * annuity(i = 0.06 / 12, n = 18, type = "arrears")
6. Un concesionario de automóviles ofrece un auto nuevo con un pago inicial de $8000 y 36 pagos mensuales de $680 cada uno, con interés del 12% capitalizable mensualmente ¿Cuál es el valor de contado del auto?

  8000 + 680 * annuity(i = 0.12 / 12, n = 36, type = "arrears")

7. El 1 de mayo de 2000 una persona depositó $500 en una cuenta de ahorros que paga el 3% convertible semestralmente y continuó haciendo depósitos similares cada 6 meses desde entonces. Después del 1 de mayo de 2003, el banco elevó el interés al 4% convertible semestralmente. ¿Cuánto registró la cuenta precisamente después del depósito del 1 de noviembre de 2005

(500 * (1 + 0.03 / 2) ^ 6 + 
    500 * accumulatedValue(i = 0.03 / 2, n = 6, type = "arrears")) * (1 + 0.04 / 2) ^ 5 + 
  500 * accumulatedValue(i = 0.04 / 2, n = 5, type = "arrears")

