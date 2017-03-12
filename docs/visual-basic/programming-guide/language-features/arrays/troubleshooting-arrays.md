---
title: "Solucionar problemas de matrices (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], errores de compilación"
  - "matrices [Visual Basic], errores de declaración"
  - "matrices [Visual Basic], errores de inicialización"
  - "matrices [Visual Basic], solucionar problemas"
  - "solucionar problemas de matrices"
  - "solucionar problemas de Visual Basic, matrices"
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Solucionar problemas de matrices (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En esta página se muestran algunos problemas comunes que pueden aparecer al trabajar con matrices.  
  
## Errores de compilación al declarar e inicializar una matriz  
 Pueden surgir errores de compilación si se comprenden mal las reglas para declarar, crear e inicializar matrices.  Las causas más comunes de errores son las siguientes:  
  
-   Proporcionar una cláusula [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md) después de especificar longitudes de dimensión en la declaración de variables de la matriz.  En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Especificar longitudes de dimensión para más que la matriz de nivel superior de una matriz escalonada.  En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Omitir la palabra clave `New` al especificar los valores de elemento.  En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Proporcionar una cláusula `New` sin corchetes \(`{}`\).  En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## Tener acceso a una matriz fuera de límites  
 El proceso de inicializar una matriz asigna un límite superior y un límite inferior a cada dimensión.  Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión.  Si un índice está por debajo del límite inferior o por encima del límite superior, se produce una excepción <xref:System.IndexOutOfRangeException>.  El compilador no puede detectar este tipo de error, por lo que aparece un error en tiempo de ejecución.  
  
### Determinar los límites  
 Si otro componente pasa una matriz al código, por ejemplo como un argumento de procedimiento, no se conoce el tamaño de la matriz o la longitud de sus dimensiones.  Siempre se debe determinar el límite superior para cada dimensión de una matriz antes de intentar tener acceso a cualquier elemento.  Si la matriz se ha creado por un medio distinto de una cláusula `New` de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], el límite inferior podría ser distinto de cero y es más seguro determinar también ese límite inferior.  
  
### Especificar la dimensión  
 Al determinar los límites de una matriz multidimensional, tenga cuidado de cómo especifica la dimensión.  Los parámetros `dimension` de los métodos <xref:System.Array.GetLowerBound%2A> y <xref:System.Array.GetUpperBound%2A> están basados en cero, mientras que los parámetros `Rank` de las funciones <xref:Microsoft.VisualBasic.Information.LBound%2A> y <xref:Microsoft.VisualBasic.Information.UBound%2A> de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] están basados en uno.  
  
## Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)