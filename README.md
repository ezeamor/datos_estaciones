# datos_estaciones

####################################################

# LECTURA DE DATOS DE PRECIPITACION DE ESTACIONES
# DE LA RED COMUNITARIA BERMEJO.

####################################################

graphics.off() # Elimina congifuracion de graficos previos.
setwd("/home/ezequiel.amor")

# Libreria a usar en este programa.

library(openxlsx) # Permite leer los archivos excel.

####################################################

# LECTURA DE DATOS DE PRECIPITACION MENSUAL.

####################################################

# En primer lugar tengo que seleccionar los datos de precipitacion mensual en el
# mismo periodo que las fechas de pronostico (NOV 2020 - ABR 2023). Esos datos 
# se extraen tanto de los datos de Resistencia como de las estaciones de la RCB.

# ESTACION RESISTENCIA.

PP_mensual_RESISTENCIA <- c()

PP_mensual_RESISTENCIA[1]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2020-11")])
PP_mensual_RESISTENCIA[2]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2020-12")])
PP_mensual_RESISTENCIA[3]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-01")])
PP_mensual_RESISTENCIA[4]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-02")])
PP_mensual_RESISTENCIA[5]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-03")])
PP_mensual_RESISTENCIA[6]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-04")])
PP_mensual_RESISTENCIA[7]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-05")])
PP_mensual_RESISTENCIA[8]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-06")])
PP_mensual_RESISTENCIA[9]  <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-07")])
PP_mensual_RESISTENCIA[10] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-08")])
PP_mensual_RESISTENCIA[11] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-09")])
PP_mensual_RESISTENCIA[12] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-10")])
PP_mensual_RESISTENCIA[13] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-11")])
PP_mensual_RESISTENCIA[14] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2021-12")])
PP_mensual_RESISTENCIA[15] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-01")])
PP_mensual_RESISTENCIA[16] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-02")])
PP_mensual_RESISTENCIA[17] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-03")])
PP_mensual_RESISTENCIA[18] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-04")])
PP_mensual_RESISTENCIA[19] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-05")])
PP_mensual_RESISTENCIA[20] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-06")])
PP_mensual_RESISTENCIA[21] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-07")])
PP_mensual_RESISTENCIA[22] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-08")])
PP_mensual_RESISTENCIA[23] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-09")])
PP_mensual_RESISTENCIA[24] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-10")])
PP_mensual_RESISTENCIA[25] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-11")])
PP_mensual_RESISTENCIA[26] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2022-12")])
PP_mensual_RESISTENCIA[27] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2023-01")])
PP_mensual_RESISTENCIA[28] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2023-02")])
PP_mensual_RESISTENCIA[29] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2023-03")])
PP_mensual_RESISTENCIA[30] <- sum(datos_PP$PP[which(substr(datos_PP$Fechas,1,7) == "2023-04")])

# Genero un dataframe donde voy a guardar toda la información. Guardo en primer 
# lugar los datos mensuales de Resistencia.

PP_mensual <- data.frame("Resistencia"=PP_mensual_RESISTENCIA)

# Ahora trabajo con los datos de las estaciones RCB. Los datos vienen en archivos
# excel, entonces con "sheet" indico el nombre de la hoja a leer, con "cols" las
# columnas a leer y con "rows" las filas a leer.

# ESTACION MONCHOLO.

PP_mensual_MONCHOLO_2020 <- read.xlsx("5_Moncholo.xlsx",sheet="2020",cols=12:13,rows=37,colNames=F)
PP_mensual_MONCHOLO_2021 <- read.xlsx("5_Moncholo.xlsx",sheet="2021",cols=2:13,rows=37,colNames=F)
PP_mensual_MONCHOLO_2022 <- read.xlsx("5_Moncholo.xlsx",sheet="2022",cols=2:13,rows=37,colNames=F)
PP_mensual_MONCHOLO_2023 <- read.xlsx("5_Moncholo.xlsx",sheet="2023",cols=2:5,rows=37,colNames=F)


PP_mensual_MONCHOLO <- as.vector(c(PP_mensual_MONCHOLO_2020$X1,PP_mensual_MONCHOLO_2020$X2,
                                   PP_mensual_MONCHOLO_2021$X1,PP_mensual_MONCHOLO_2021$X2,
                                   PP_mensual_MONCHOLO_2021$X3,PP_mensual_MONCHOLO_2021$X4,
                                   PP_mensual_MONCHOLO_2021$X5,PP_mensual_MONCHOLO_2021$X6,
                                   PP_mensual_MONCHOLO_2021$X7,PP_mensual_MONCHOLO_2021$X8,
                                   PP_mensual_MONCHOLO_2021$X9,PP_mensual_MONCHOLO_2021$X10,
                                   PP_mensual_MONCHOLO_2021$X11,PP_mensual_MONCHOLO_2021$X12,
                                   PP_mensual_MONCHOLO_2022$X1,PP_mensual_MONCHOLO_2022$X2,
                                   PP_mensual_MONCHOLO_2022$X3,PP_mensual_MONCHOLO_2022$X4,
                                   PP_mensual_MONCHOLO_2022$X5,PP_mensual_MONCHOLO_2022$X6,
                                   PP_mensual_MONCHOLO_2022$X7,PP_mensual_MONCHOLO_2022$X8,
                                   PP_mensual_MONCHOLO_2022$X9,PP_mensual_MONCHOLO_2022$X10,
                                   PP_mensual_MONCHOLO_2022$X11,PP_mensual_MONCHOLO_2022$X12,
                                   PP_mensual_MONCHOLO_2023$X1,PP_mensual_MONCHOLO_2023$X2,
                                   PP_mensual_MONCHOLO_2023$X3,PP_mensual_MONCHOLO_2023$X4))

# Agrego los datos al dataframe

PP_mensual$Moncholo <- PP_mensual_MONCHOLO

# ESTACION GENERAL VEDIA.

PP_mensual_GRALVEDIA_2020 <- read.xlsx("11_General_Vedia.xlsx",sheet="2020",cols=12:13,rows=37,colNames=F)
PP_mensual_GRALVEDIA_2021 <- read.xlsx("11_General_Vedia.xlsx",sheet="2021",cols=2:13,rows=37,colNames=F)
PP_mensual_GRALVEDIA_2022 <- read.xlsx("11_General_Vedia.xlsx",sheet="2022",cols=2:13,rows=37,colNames=F)
PP_mensual_GRALVEDIA_2023 <- read.xlsx("11_General_Vedia.xlsx",sheet="2023",cols=2:5,rows=37,colNames=F)

PP_mensual_GRALVEDIA <- as.vector(c(PP_mensual_GRALVEDIA_2020$X1,PP_mensual_GRALVEDIA_2020$X2,
                                    PP_mensual_GRALVEDIA_2021$X1,PP_mensual_GRALVEDIA_2021$X2,
                                    PP_mensual_GRALVEDIA_2021$X3,PP_mensual_GRALVEDIA_2021$X4,
                                    PP_mensual_GRALVEDIA_2021$X5,PP_mensual_GRALVEDIA_2021$X6,
                                    PP_mensual_GRALVEDIA_2021$X7,PP_mensual_GRALVEDIA_2021$X8,
                                    PP_mensual_GRALVEDIA_2021$X9,PP_mensual_GRALVEDIA_2021$X10,
                                    PP_mensual_GRALVEDIA_2021$X11,PP_mensual_GRALVEDIA_2021$X12,
                                    PP_mensual_GRALVEDIA_2022$X1,PP_mensual_GRALVEDIA_2022$X2,
                                    PP_mensual_GRALVEDIA_2022$X3,PP_mensual_GRALVEDIA_2022$X4,
                                    PP_mensual_GRALVEDIA_2022$X5,PP_mensual_GRALVEDIA_2022$X6,
                                    PP_mensual_GRALVEDIA_2022$X7,PP_mensual_GRALVEDIA_2022$X8,
                                    PP_mensual_GRALVEDIA_2022$X9,PP_mensual_GRALVEDIA_2022$X10,
                                    PP_mensual_GRALVEDIA_2022$X11,PP_mensual_GRALVEDIA_2022$X12,
                                    PP_mensual_GRALVEDIA_2023$X1,PP_mensual_GRALVEDIA_2023$X2,
                                    PP_mensual_GRALVEDIA_2023$X3,PP_mensual_GRALVEDIA_2023$X4))

# Agrego los datos al dataframe.

PP_mensual$GralVedia <- PP_mensual_GRALVEDIA

# ESTACION LOTE 16.

PP_mensual_LOTE16_2020 <- read.xlsx("12_Lote16.xlsx",sheet="2020",cols=12:13,rows=37,colNames=F)
PP_mensual_LOTE16_2021 <- read.xlsx("12_Lote16.xlsx",sheet="2021",cols=2:13,rows=37,colNames=F)
PP_mensual_LOTE16_2022 <- read.xlsx("12_Lote16.xlsx",sheet="2022",cols=2:13,rows=37,colNames=F)
PP_mensual_LOTE16_2023 <- read.xlsx("12_Lote16.xlsx",sheet="2023",cols=2:5,rows=37,colNames=F)

PP_mensual_LOTE16 <- as.vector(c(PP_mensual_LOTE16_2020$X1,PP_mensual_LOTE16_2020$X2,
                                 PP_mensual_LOTE16_2021$X1,PP_mensual_LOTE16_2021$X2,
                                 PP_mensual_LOTE16_2021$X3,PP_mensual_LOTE16_2021$X4,
                                 PP_mensual_LOTE16_2021$X5,PP_mensual_LOTE16_2021$X6,
                                 PP_mensual_LOTE16_2021$X7,PP_mensual_LOTE16_2021$X8,
                                 PP_mensual_LOTE16_2021$X9,PP_mensual_LOTE16_2021$X10,
                                 PP_mensual_LOTE16_2021$X11,PP_mensual_LOTE16_2021$X12,
                                 PP_mensual_LOTE16_2022$X1,PP_mensual_LOTE16_2022$X2,
                                 PP_mensual_LOTE16_2022$X3,PP_mensual_LOTE16_2022$X4,
                                 PP_mensual_LOTE16_2022$X5,PP_mensual_LOTE16_2022$X6,
                                 PP_mensual_LOTE16_2022$X7,PP_mensual_LOTE16_2022$X8,
                                 PP_mensual_LOTE16_2022$X9,PP_mensual_LOTE16_2022$X10,
                                 PP_mensual_LOTE16_2022$X11,PP_mensual_LOTE16_2022$X12,
                                 PP_mensual_LOTE16_2023$X1,PP_mensual_LOTE16_2023$X2,
                                 PP_mensual_LOTE16_2023$X3,PP_mensual_LOTE16_2023$X4))

# Agrego los datos al dataframe.

PP_mensual$Lote16 <- PP_mensual_LOTE16

# ESTACION PUERTO BERMEJO KM 90.

PP_mensual_PTOBJOKM90_2020 <- read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2020",cols=12:13,rows=37,colNames=F)
PP_mensual_PTOBJOKM90_2021 <- read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=2:13,rows=37,colNames=F)
PP_mensual_PTOBJOKM90_2022 <- read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=2:13,rows=37,colNames=F)
PP_mensual_PTOBJOKM90_2023 <- read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2023",cols=2:5,rows=37,colNames=F)

PP_mensual_PTOBJOKM90 <- as.vector(c(PP_mensual_PTOBJOKM90_2020$X1,PP_mensual_PTOBJOKM90_2020$X2,
                                     PP_mensual_PTOBJOKM90_2021$X1,PP_mensual_PTOBJOKM90_2021$X2,
                                     PP_mensual_PTOBJOKM90_2021$X3,PP_mensual_PTOBJOKM90_2021$X4,
                                     PP_mensual_PTOBJOKM90_2021$X5,PP_mensual_PTOBJOKM90_2021$X6,
                                     PP_mensual_PTOBJOKM90_2021$X7,PP_mensual_PTOBJOKM90_2021$X8,
                                     PP_mensual_PTOBJOKM90_2021$X9,PP_mensual_PTOBJOKM90_2021$X10,
                                     PP_mensual_PTOBJOKM90_2021$X11,PP_mensual_PTOBJOKM90_2021$X12,
                                     PP_mensual_PTOBJOKM90_2022$X1,PP_mensual_PTOBJOKM90_2022$X2,
                                     PP_mensual_PTOBJOKM90_2022$X3,PP_mensual_PTOBJOKM90_2022$X4,
                                     PP_mensual_PTOBJOKM90_2022$X5,PP_mensual_PTOBJOKM90_2022$X6,
                                     PP_mensual_PTOBJOKM90_2022$X7,PP_mensual_PTOBJOKM90_2022$X8,
                                     PP_mensual_PTOBJOKM90_2022$X9,PP_mensual_PTOBJOKM90_2022$X10,
                                     PP_mensual_PTOBJOKM90_2022$X11,PP_mensual_PTOBJOKM90_2022$X12,
                                     PP_mensual_PTOBJOKM90_2023$X1,PP_mensual_PTOBJOKM90_2023$X2,
                                     PP_mensual_PTOBJOKM90_2023$X3,PP_mensual_PTOBJOKM90_2023$X4))

# Agrego los datos al dataframe.

PP_mensual$PtoBermejokm90 <- PP_mensual_PTOBJOKM90

# ESTACION TRES HORQUETAS ROLON.

PP_mensual_TRESHR_2020 <- read.xlsx("26_Tres_H.ROLON.xlsx",sheet="2020",cols=12:13,rows=37,colNames=F)
PP_mensual_TRESHR_2021 <- read.xlsx("26_Tres_H.ROLON.xlsx",sheet="2021",cols=2:13,rows=37,colNames=F)
PP_mensual_TRESHR_2022 <- read.xlsx("26_Tres_H.ROLON.xlsx",sheet="2022",cols=2:13,rows=37,colNames=F)
PP_mensual_TRESHR_2023 <- read.xlsx("26_Tres_H.ROLON.xlsx",sheet="2023",cols=2:5,rows=37,colNames=F)

PP_mensual_TRESHR <- as.vector(c(PP_mensual_TRESHR_2020$X1,PP_mensual_TRESHR_2020$X2,
                                 PP_mensual_TRESHR_2021$X1,PP_mensual_TRESHR_2021$X2,
                                 PP_mensual_TRESHR_2021$X3,PP_mensual_TRESHR_2021$X4,
                                 PP_mensual_TRESHR_2021$X5,PP_mensual_TRESHR_2021$X6,
                                 PP_mensual_TRESHR_2021$X7,PP_mensual_TRESHR_2021$X8,
                                 PP_mensual_TRESHR_2021$X9,PP_mensual_TRESHR_2021$X10,
                                 PP_mensual_TRESHR_2021$X11,PP_mensual_TRESHR_2021$X12,
                                 PP_mensual_TRESHR_2022$X1,PP_mensual_TRESHR_2022$X2,
                                 PP_mensual_TRESHR_2022$X3,PP_mensual_TRESHR_2022$X4,
                                 PP_mensual_TRESHR_2022$X5,PP_mensual_TRESHR_2022$X6,
                                 PP_mensual_TRESHR_2022$X7,PP_mensual_TRESHR_2022$X8,
                                 PP_mensual_TRESHR_2022$X9,PP_mensual_TRESHR_2022$X10,
                                 PP_mensual_TRESHR_2022$X11,PP_mensual_TRESHR_2022$X12,
                                 PP_mensual_TRESHR_2023$X1,PP_mensual_TRESHR_2023$X2,
                                 PP_mensual_TRESHR_2023$X3,PP_mensual_TRESHR_2023$X4))

# Agrego los datos al dataframe.

PP_mensual$TresHorquetasRolon <- PP_mensual_TRESHR

# Agrego también una columna con el numero de los meses.

PP_mensual$mes <- c(1:30)

# Estos datos se usaran en el programa "graficos" para plotear los valores 
# mensuales de precipitacion y asi poder comparar lo que sucede en Resistencia con
# las estaciones de la RCB.

####################################################

# CALCULO DE ACUMULADO PARA LA SEMANA 2.

####################################################

# Extraigo del archivo de precipitación de cada estacion para calcular los 
# acumulados de la semana 2 correspondientes a las mismas fechas de referencia 
# que para Resistencia Aero.

# IMPORTANTE: Para no repetir el programa, se debera modificar el nombre de la 
# estacion que se este trabajando en todas las variables que se usen a continuacion 
# y del archivo excel que se lea en "datos_PP_...".

# Necesito los datos de precipitacion entre el 20/11/2020 y el 27/4/2023 para
# calcular los acumulados. 
# Si hay algun dato que falta (en algunos archivos hay datos de precipitacion que 
# estan vacios) agregar un cero por cada dato faltante para que el largo de datos
# sea el correcto para aplicar los calculos. Al poner ceros en el mes donde falten datos, 
# no se modificaran las cuentas. (Por ejemplo, en los datos de Puerto Bermejo km 90 
# falta el dato del 31 de marzo, entonces luego de los datos de marzo 2023 se 
# agrega un cero para que se lean 31 datos totales del mes).

datos_PP_PtoBjokm90 <- rbind(read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2020",cols=12,rows=23:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2020",cols=13,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=2,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=3,rows=4:31,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=4,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=5,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=6,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=7,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=8,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=9,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=10,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=11,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=12,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2021",cols=13,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=2,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=3,rows=4:31,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=4,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=5,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=6,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=7,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=8,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=9,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=10,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=11,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=12,rows=4:33,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2022",cols=13,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2023",cols=2,rows=4:34,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2023",cols=3,rows=4:31,colNames=F),
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2023",cols=4,rows=4:34,colNames=F),0,
                        read.xlsx("24_Puerto_bermejo_km90.xlsx",sheet="2023",cols=5,rows=4:30,colNames=F))

colnames(datos_PP_PtoBjokm90) <- ("PP")

# Si hay datos faltantes los asigno como NA.

datos_PP_PtoBjokm90[datos_PP_PtoBjokm90 == "DF"] <- NA

# Calculo los acumulados correspondientes.

# Si los datos se guardan como "character", los paso a "numeric". Sino saltear
# la siguiente linea.

datos_PP_Lote16 <- as.numeric(datos_PP_Lote16[,1])

acumulados_PtoBjokm90 <- c()

# Si hay dato faltante, agregar na.rm=T a la suma, sino lo dejo como esta.
# Si no tengo un vector de acumulados, recordar agregar en el for la dimension de 
# la columna para leer el largo y los datos del dataframe.

for(i in 1:length(datos_PP_PtoBjokm90[,1])) {
  acumulados_PtoBjokm90[i] <- sum(datos_PP_PtoBjokm90[(1+(i-1)):(7+(i-1)),1])
}

# Si no tengo datos faltantes, borro los ultimos 6 datos que se guardan como NAs.
# Si no es el caso, no correr la siguiente linea.

acumulados_PtoBjokm90 <- acumulados_PtoBjokm90[-which(is.na(acumulados_PtoBjokm90))]

# Si tengo dato faltante, borro lo ultimos 6 datos que se que son incorrectos
# pero que ahora no se reconocen como NAs.
# Si no es el caso, no correr la siguiente linea.

acumulados_Lote16 <- acumulados_Lote16[-c(884:889)]

# Guardo la información en un dataframe nuevo.

datos_totales_PtoBjokm90 <- data.frame("A"=fechas_totales,"B"=acumulados_PtoBjokm90)

# Me quedo solo con las semanas en que tengo pronotico.

acumulados_PtoBjokm90 <- datos_totales_PtoBjokm90$B[which(fechas_totales %in% fechas_prono)]

# Guardo la informacion en el mismo dataframe donde ya tenia los datos de 
# Resistencia Aero y alguna otra estacion, generado en el programa "datos_PP_Prono".

PP_acum$Acum_S2_PtoBermejokm90 <- acumulados_PtoBjokm90

#####################################################

# CALCULO DE OCURRENCIA DE PRECIPITACION ACUMULADA

#####################################################

PP_1mm_Promedio_RCB   <- c()
PP_20mm_Promedio_RCB <- c()
PP_50mm_Promedio_RCB  <- c()
PP_100mm_Promedio_RCB <- c()

for(i in 1:length(PP_acum$Acum_S2_Promedio_RCB)){
  if(PP_acum$Acum_S2_Promedio_RCB[i]>=1) {
    PP_1mm_Promedio_RCB[i] <- 1
  } else {
    PP_1mm_Promedio_RCB[i] <- 0}
}

for(i in 1:length(PP_acum$Acum_S2_Promedio_RCB)){
  if(PP_acum$Acum_S2_Promedio_RCB[i]>=20) {
    PP_20mm_Promedio_RCB[i] <- 1
  } else {
    PP_20mm_Promedio_RCB[i] <- 0}
}

for(i in 1:length(PP_acum$Acum_S2_Promedio_RCB)){
  if(PP_acum$Acum_S2_Promedio_RCB[i]>=50) {
    PP_50mm_Promedio_RCB[i] <- 1
  } else {
    PP_50mm_Promedio_RCB[i] <- 0}
}

for(i in 1:length(PP_acum$Acum_S2_Promedio_RCB)){
  if(PP_acum$Acum_S2_Promedio_RCB[i]>=100) {
    PP_100mm_Promedio_RCB[i] <- 1
  } else {
    PP_100mm_Promedio_RCB[i] <- 0}
}

Ocurrencias_estaciones$Ocu_1mm_Promedio_RCB   <- PP_1mm_Promedio_RCB
Ocurrencias_estaciones$Ocu_20mm_Promedio_RCB  <- PP_20mm_Promedio_RCB
Ocurrencias_estaciones$Ocu_50mm_Promedio_RCB  <- PP_50mm_Promedio_RCB
Ocurrencias_estaciones$Ocu_100mm_Promedio_RCB <- PP_100mm_Promedio_RCB

#####################################################

# CALCULO DE PRECIPITACION ACUMULADA PROMEDIO PARA
# LAS 5 ESTACIONES DE LA RCB.

#####################################################

acumulados_prom <- c()

for(i in 1:length(PP_acum[,1])) {
  acumulados_prom[i] <- mean(c(PP_acum$Acum_S2_TresHoquetas2[i],
                             PP_acum$Acum_S2_Moncholo[i],
                             PP_acum$Acum_S2_GralVedia[i],
                             PP_acum$Acum_S2_Lote16[i],
                             PP_acum$Acum_S2_PtoBermejokm90[i]))
}

PP_acum$Acum_S2_Promedio_RCB <- acumulados_prom
