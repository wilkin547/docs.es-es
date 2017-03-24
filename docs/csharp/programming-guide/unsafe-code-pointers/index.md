---
title: "C&#243;digo no seguro y punteros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "seguridad [C#], seguridad de tipos"
  - "Lenguaje C#, código no seguro"
  - "seguridad de tipos [C#]"
  - "unsafe (palabra clave) [C#]"
  - "código no seguro [C#]"
  - "lenguaje C#, punteros"
  - "punteros [C#], acerca de los punteros"
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# C&#243;digo no seguro y punteros (Gu&#237;a de programaci&#243;n de C#)
Para mantener la seguridad de tipos y la seguridad, C\# no admite la aritmética con punteros de manera predeterminada.  Sin embargo, si utiliza la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), puede definir un contexto no seguro en el que se pueden utilizar punteros.  Para obtener más información sobre los punteros, vea el tema [Tipos de puntero \(Guía de programación de C\#\)](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  En el Common Language Runtime \(CLR\), se hace referencia al código no seguro como código no comprobable.  El código no seguro en C\# no es necesariamente peligroso; sólo es código cuya seguridad no puede ser comprobada por el CLR.  Por consiguiente, el CLR sólo ejecutará código no seguro si se encuentra en un ensamblado de plena confianza.  Si utiliza el código no seguro, es su responsabilidad garantizar que su código no introduce riesgos de seguridad o errores de puntero.  
  
## Información general sobre código no seguro  
 El código no seguro tiene las propiedades siguientes:  
  
-   Los métodos, tipos y bloques de código se pueden definir como no seguros.  
  
-   En algunos casos, el código no seguro puede aumentar el rendimiento de una aplicación al quitar las comprobaciones de los límites de la matriz  
  
-   Se requiere código no seguro al llamar a funciones nativas que requieren punteros.  
  
-   El uso de código no seguro implica riesgos de seguridad y de estabilidad.  
  
-   Para que C\# compile código no seguro, la aplicación se debe compilar con [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  
  
## Secciones relacionadas  
 Para obtener más información, vea:  
  
-   [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Cómo: Utilizar punteros para copiar una matriz de bytes](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [no seguras](../../../csharp/language-reference/keywords/unsafe.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)