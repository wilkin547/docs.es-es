---
title: "C&#243;mo: Asignar una matriz a otra (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "matrices [Visual Basic], asignar"
  - "matrices [Visual Basic], covarianza"
  - "covarianza, matrices"
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Asignar una matriz a otra (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puesto que las matrices son objetos, puede utilizarlas en instrucciones de asignación como cualquier otro tipo de objeto.  Una variable de matriz contiene un puntero a los datos que constituyen los elementos de matriz, y a la información de rango y longitud; una asignación copia sólo este puntero.  
  
### Para asignar una matriz a otra  
  
1.  Asegúrese de que las dos matrices tienen el mismo rango \(número de dimensiones\) y tipos de datos de elementos compatibles.  
  
2.  Utilice una instrucción de asignación estándar para asignar la matriz de origen a la matriz de destino.  No agregue paréntesis detrás del nombre de las matrices.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 En la asignación de una matriz a otra, se aplican las siguientes reglas:  
  
-   **Rangos iguales.** El rango \(número de dimensiones\) de la matriz de destino debe coincidir con el de la matriz de origen.  
  
     Siempre que los rangos de las dos matrices sean iguales, no es necesario que las dimensiones sean iguales.  El número de elementos de una dimensión dada puede cambiar durante la asignación.  
  
-   **Tipos de elementos.** Ambas matrices deben tener elementos de *tipo de referencia* o bien ambas matrices deben tener elementos de *tipo de valor*.  Para obtener más información, vea [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Si ambas matrices tienen elementos de tipo de valor, los tipos de datos deben coincidir exactamente.  La única excepción a esto es que puede asignar una matriz de elementos `Enum` a una matriz del tipo base de esta `Enum`.  
  
    -   Si ambas matrices tienen elementos de tipo de referencia, el tipo de elemento de origen debe derivar del tipo de elemento de destino.  Cuando éste es el caso, las dos matrices tienen la misma relación de herencia que sus elementos.  Esto se denomina *covarianza de matriz*.  
  
 El compilador notifica un error si las reglas anteriores no se cumplen, por ejemplo, si los tipos de datos no son compatibles o si los rangos no son iguales.  Se puede incluir control de errores en el código para comprobar si las matrices son compatibles antes de intentar realizar la asignación.  También puede utilizar la palabra clave [TryCast \(Operador\)](../../../../visual-basic/language-reference/operators/trycast-operator.md) si desea evitar que se produzca una excepción.  
  
## Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Solucionar problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Enum \(Instrucción\)](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)