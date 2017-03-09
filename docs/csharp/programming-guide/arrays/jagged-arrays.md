---
title: "Matrices escalonadas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], escalonadas"
  - "matrices escalonadas [C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Matrices escalonadas (Gu&#237;a de programaci&#243;n de C#)
Una matriz escalonada es una matriz cuyos elementos son matrices.  Los elementos de una matriz escalonada pueden ser de diferentes dimensiones y tamaños.  Una matriz escalonada se denomina también "matriz de matrices". Los ejemplos siguientes muestran cómo declarar, inicializar y tener acceso a las matrices escalonadas.  
  
 A continuación, se muestra la declaración de una matriz unidimensional con tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_1.cs)]  
  
 Para poder utilizar `jaggedArray`, se deben inicializar sus elementos.  Los elementos se pueden inicializar de la siguiente manera:  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_2.cs)]  
  
 Cada elemento es una matriz unidimensional de enteros.  El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.  
  
 También se pueden utilizar inicializadores para rellenar los elementos de la matriz con valores, en cuyo caso no es necesario especificar el tamaño de la matriz:  Por ejemplo:  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_3.cs)]  
  
 Asimismo, se puede inicializar la matriz en el momento de la declaración de este modo:  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_4.cs)]  
  
 Puede utilizar el formulario abreviado siguiente.  Observe que no se puede omitir el operador `new` de la inicialización de elementos ya que no existe una inicialización predeterminada para los elementos:  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_5.cs)]  
  
 Una matriz escalonada es una matriz de matrices y por consiguiente sus elementos son tipos de referencia y se inicializan en `null`.  
  
 El acceso a elementos individuales de la matriz se realiza como en los siguientes ejemplos:  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_6.cs)]  
  
 Es posible combinar matrices multidimensionales con matrices escalonadas.  A continuación, se muestra la declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensionales de diferentes tamaños.  Para obtener más información sobre las matrices bidimensionales, vea [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_7.cs)]  
  
 Puede obtener acceso a los elementos individuales como se indica en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz \(valor `5`\):  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_8.cs)]  
  
 El método `Length` devuelve el número de matrices contenido en la matriz escalonada.  Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_9.cs)]  
  
 devuelve un valor de 3.  
  
## Ejemplo  
 En este ejemplo, se compila una matriz cuyos elementos son también matrices.  Cada uno de los elementos de la matriz tiene un tamaño diferente.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/csharp/jagged-arrays_10.cs)]  
  
## Vea también  
 <xref:System.Array>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)