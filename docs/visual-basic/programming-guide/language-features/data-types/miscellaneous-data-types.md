---
title: "Tipos de datos variados (Visual Basic) | Microsoft Docs"
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
  - "tipos de datos [Visual Basic], elegir"
  - "Object (tipo de datos), tipos de datos"
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Tipos de datos variados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona varios tipos de datos que no están orientados a números o caracteres.  En lugar de ello, tratan con datos especializados como valores de tipo sí\/no, valores de fecha y hora, y direcciones de objetos.  
  
 Para ver una tabla en la que se muestra una comparación en paralelo de los tipos de datos de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Boolean \(Tipo\)  
 [Boolean \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) es un valor sin signo interpretado como `True` o `False`.  El ancho de sus datos depende de la plataforma de implementación.  Si una variable puede contener sólo valores de dos estados como verdadero\/falso, sí\/no, o activado\/desactivado, declárela como `Boolean`.  
  
## Date \(Tipo\)  
 [Date \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora.  Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el principio \(12:00 a.m.\) del 1 de enero del año 1 del calendario gregoriano.  Si una variable puede contener un valor de fecha, un valor de hora o ambos, declárela como `Date`.  
  
## Object \(Tipo\)  
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md) es una dirección de 32 bits que apunta a una instancia de objeto dentro de la aplicación o en alguna otra aplicación.  Una variable `Object` puede hacer referencia a cualquier objeto que la aplicación reconoce o a datos de cualquier tipo de datos.  Esto incluye los *tipos de valor*, como `Integer`, `Boolean`, y las instancias de la estructura, y *los tipos de referencia*, que son instancias de los objetos creados a partir de clases como `String` y <xref:System.Windows.Forms.Form>, y las instancias de la matriz.  
  
 Si una variable almacena un puntero a una instancia de una clase que no conoce en tiempo de compilación o si puede señalar a los datos de distintos tipos de datos, declárela como `Object`.  
  
 La ventaja del tipo de datos de `Object` es que puede utilizarlo para almacenar datos de cualquier tipo de datos.  El inconveniente es que provoca operaciones adicionales que exigen más tiempo de ejecución y ralentizan su aplicación.  Si utiliza una variable `Object` para los tipos de valor, provoca una *conversión boxing* y una *conversión unboxing*.  Si lo utiliza para los tipos de referencia, provoca un *enlace en tiempo de ejecución*.  
  
## Vea también  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)