---
title: "Convenciones de nomenclatura de Visual Basic | Microsoft Docs"
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
  - "convenciones, código en Visual Basic"
  - "nombres, convenciones de nomenclatura"
  - "nombres, reglas de Visual Basic"
  - "convenciones de nomenclatura"
  - "convenciones de nomenclatura, clases"
  - "convenciones de nomenclatura, Visual Basic"
  - "código de Visual Basic, convenciones de nomenclatura"
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Convenciones de nomenclatura de Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Al dar nombre a un elemento de una aplicación de Visual Basic, el primer carácter del nombre debe ser un carácter alfabético o un guión de subrayado.  Tenga en cuenta, sin embargo, que los nombres que empiezan con un guión de subrayado no cumplen las normas de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  
  
 A la nomenclatura se aplican las siguientes sugerencias.  
  
-   Empiece cada palabra independiente de un nombre con una letra mayúscula, como en `FindLastRecord` y `RedrawMyForm`.  
  
-   Empiece los nombres de método y de función con un verbo, como en `InitNameArray` o `CloseDialog`.  
  
-   Empiece los nombres de clase, estructura, módulo y propiedad con un nombre, como en `EmployeeName` o `CarAccessory`.  
  
-   Empiece los nombres de interfaz con el prefijo "I", seguido de un nombre o una frase nominal, como `IComponent`, o con un adjetivo que describa el comportamiento de la interfaz, como `IPersistable`.  No utilice el subrayado, y utilice lo menos posible las abreviaturas, ya que pueden causar confusiones.  
  
-   Empiece los nombres de controlador de eventos con un nombre que describa el tipo de evento seguido por el sufijo "`EventHandler`", como en "`MouseEventHandler`".  
  
-   En nombres de clases de argumento de evento, incluya el sufijo "`EventArgs`".  
  
-   Si un evento tiene un concepto de “antes” o “después”, utilice un sufijo en tiempo presente o pasado, como en "`ControlAdd`" o "`ControlAdded`".  
  
-   Para términos largos o utilizados con frecuencia, utilice abreviaturas para mantener las longitudes de los nombres dentro un límite razonable, por ejemplo, "HTML" en lugar de "Lenguaje de marcado de hipertexto".  En general, los nombres de variable con más de 32 caracteres son difíciles de leer en una pantalla configurada para una resolución baja.  Además, asegúrese de que sus abreviaturas sean coherentes a lo largo de toda la aplicación.  Si utiliza indistinta y aleatoriamente "HTML" y "Lenguaje de marcado de hipertexto" en un mismo proyecto, puede provocar confusión.  
  
-   Evite utilizar nombres que en un entorno interno sean iguales que otros nombres de un entorno externo.  Se producirán errores si se obtiene acceso a la variable equivocada.  Si se produce un conflicto entre una variable y la palabra clave del mismo nombre, debe identificar la palabra clave poniéndole delante la biblioteca de tipos adecuada.  Por ejemplo, si tiene una variable denominada `Date`, sólo puede utilizar la función intrínseca `Date` llamando a <xref:System.DateTime.Date%2A?displayProperty=fullName>.  
  
## Vea también  
 [Palabras clave como nombres de elementos en código](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)   
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)