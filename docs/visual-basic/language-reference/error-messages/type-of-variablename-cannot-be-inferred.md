---
title: "No se puede inferir el tipo de &#39;&lt;nombreDeVariable&gt;&#39; porque los l&#237;mites del bucle y la variable step no se convierten en el mismo tipo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30982"
  - "vbc30982"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30982"
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# No se puede inferir el tipo de &#39;&lt;nombreDeVariable&gt;&#39; porque los l&#237;mites del bucle y la variable step no se convierten en el mismo tipo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ha escrito un bucle `For...Next` en el que el compilador no puede deducir un tipo de datos para la variable de control de bucle porque las siguientes condiciones son verdaderas:  
  
-   El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As`.  
  
-   Los límites del bucle y variable step contienen por lo menos dos tipos de datos.  
  
-   No existe ninguna conversión estándar entre los tipos de datos.  
  
 Por consiguiente, el compilador no puede deducir el tipo de datos de la variable de control de un bucle.  
  
 En el ejemplo siguiente, la variable step es un carácter y ambos límites del bucle son enteros.  Dado que no hay ninguna conversión estándar entre caracteres y enteros, se informa de este error.  
  
```vb#  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **Id. de error:** BC30982  
  
### Para corregir este error  
  
-   Cambie los tipos de los límites del bucle y de la variable step de forma que por lo menos uno de ellos sea un tipo al que amplían los demás.  En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     \-O bien\-  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Use las funciones de conversión explícitas para convertir los límites del bucle y la variable step a los tipos adecuados.  En el ejemplo anterior, aplique la función de `Val` a `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)