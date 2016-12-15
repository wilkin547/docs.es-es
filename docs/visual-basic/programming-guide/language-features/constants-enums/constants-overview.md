---
title: "Informaci&#243;n general sobre las constantes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constantes"
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Informaci&#243;n general sobre las constantes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una constante es un nombre significativo que toma el lugar de un número o cadena que no cambia.  Las constantes almacenan valores que, como su nombre indica, permanecen iguales durante la ejecución de una aplicación.  Puede mejorar considerablemente la legibilidad del código y facilitar su mantenimiento mediante constantes.  Utilícelas en código que contiene valores que reaparecen o que dependen de ciertos números que son difíciles de recordar o que no tienen un significado evidente.  
  
## Cómo crear y utilizar constantes  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] contiene varias constantes predefinidas, que se utilizan principalmente para operaciones de impresión y presentación.  Puede crear también sus propias constantes con la instrucción `Const`, utilizando las mismas directrices que en la creación de nombres de variables.  Si `Option Strict` es `On`, debe declarar el tipo de constante explícitamente.  
  
 El ámbito de una constante, que es el conjunto de todo el código que puede hacer referencia a ella sin calificar su nombre, es igual al de una variable declarada en la misma ubicación.  Para crear una constante que exista en el ámbito de un procedimiento concreto, declárela dentro de dicho procedimiento.  Para crear una constante disponible en toda la aplicación, declárela con la palabra clave `Public` en la sección de declaraciones de la clase.  
  
> [!NOTE]
>  Aunque las constantes son de algún modo similares a las variables, no se pueden modificar ni asignárseles valores como a éstas últimas.  
  
 Las constantes que se utilizan en el código pueden ser definidas por el modelo de objeto para los controles o componentes con los que trabaja o definidas por el usuario, es decir, creadas por éste.  
  
## Constantes en tiempo de compilación y en tiempo de ejecución  
 Una constante en tiempo de compilación se calcula cuando se compila el código, mientras que una constante en tiempo de ejecución sólo se puede calcular mientras la aplicación está en ejecución.  Una constante en tiempo de compilación tendrá el mismo valor cada vez que se ejecuta una aplicación, mientras que una constante en tiempo de ejecución puede cambiar cada vez.  Las constantes en tiempo de compilación se requieren para casos como límites de matriz, expresiones de caso o inicializadores de enumerador.  
  
## En esta sección  
  
|||  
|-|-|  
|Definición|Término|  
|[Cómo: Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Explica cómo utilizar la instrucción `Const` para declarar una constante y establecer su valor; al declarar una constante, asigna un nombre significativo al valor.|  
|[Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Describe la manera de crear sus propias constantes, información sobre ámbito y sobre cómo evitar las referencias circulares.|  
|[Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Proporciona información sobre cómo el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] inicializa las constantes cuando `Option Explicit` está desactivada.|  
|[Cómo: Agrupar valores de constantes relacionadas](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Muestra cómo se agrupan valores de constantes que están relacionados.|  
  
## Referencia  
  
|||  
|-|-|  
|Definición|Término|  
|[Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Muestra las constantes predefinidas por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md)|Describe la instrucción `Const` y su uso.|  
|[Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Describe la instrucción `Option Strict` y su uso.|  
  
## Vea también  
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)