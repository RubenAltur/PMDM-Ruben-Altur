## Anàlisi de l’estructura del projecte

En un projecte d'android destaquen 3 carpetes: 


**Manifests**: ón esta el AndroidManifest, archiu que controla tot el programa.


**java**: ón estan les activitats i la resta del codi.


**res**: ón es guarden tots els recursos i el frontend de la app

“Si volguera afegir una nova activitat, sería suficient crear el fitxer de layout i el fitxer Kotlin amb la classe?”:
No també es tindria que afegit l'activitat al arxíu AndroidManifest

## Análisi del clicle de vida i el problema de la pèrdua d’estat

La app perd el estat perquè al rotar la pantalla el que fa es destruir-la i tornar-la a crear desde 0 per tant el comptador torna a 0

## Solució a la pèrdua d’estat

Per a resoldre el problema de la pèrdua d'estat al rotar la pantalla cal guardar el estat de la app amb onSaveInstanceState(estat: Bundle)
al métode onDestroy i restaurar-lo amb onRestoreInstanceState(estat: Bundle) al métode onCreate()

## Ampliant la funcionalitat amb decrements i Reset

He copiat el codi al xml i en la main activity he creat les següents variables i metodes :

 val btReset=findViewById<Button>(R.id.btReset)
 val btResta=findViewById<Button>(R.id.btResta)

  btReset.setOnClickListener {
            comptador=0
            textViewContador.setText(comptador.toString())
        }
        btResta.setOnClickListener {
            comptador--
            textViewContador.setText(comptador.toString())
        }

## Canvis per implementar el View Binding
