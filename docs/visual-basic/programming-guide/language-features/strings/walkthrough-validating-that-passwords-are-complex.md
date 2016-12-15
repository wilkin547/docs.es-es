---
title: "Tutorial: Validar la complejidad de las contrase&#241;as (Visual Basic) | Microsoft Docs"
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
  - "String (tipo de datos), validación"
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Validar la complejidad de las contrase&#241;as (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este método comprueba algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre qué comprobaciones no supera la contraseña.  
  
 Las contraseñas se pueden utilizar en un sistema seguro para autorizar a un usuario.  Sin embargo, las contraseñas deben ser difíciles de adivinar para los usuarios no autorizados.  Los atacantes pueden utilizar un programa de *ataque de diccionario*, que recorre en iteración todas las palabras de un diccionario \(o varios diccionarios en distintos idiomas\) y prueba si alguna de las palabras funciona como contraseña de un usuario.  Las contraseñas débiles como "Ferrari" o "Barcelona" se pueden averiguar rápidamente.  Hay muchas menos posibilidades de que se adivinen las contraseñas más fuertes, como "?nUnKaseT'8oCurRir@mYcoNtrase\_n\_a3\!".  Un sistema protegido mediante contraseña debería garantizar que los usuarios eligen contraseñas seguras.  
  
 Una contraseña segura es compleja \(contiene una mezcla de mayúsculas, minúsculas, números y caracteres especiales\) y no es una palabra.  Este ejemplo muestra cómo comprobar la complejidad.  
  
## Ejemplo  
  
### Código  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## Compilar el código  
 Llame a este método pasando la cadena que contiene esa contraseña.  
  
 Para este ejemplo se necesita:  
  
-   Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>.  Agregar una instrucción `Imports` si no se incluyen nombres de miembro completos en el código.  Para obtener más información, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Seguridad  
 Si está moviendo la contraseña por una red, necesita utilizar un método seguro para transferir los datos.  Para obtener más información, vea [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md).  
  
 Puede mejorar la exactitud de la función `ValidatePassword` agregando comprobaciones de complejidad adicionales:  
  
-   Compare la contraseña y sus subcadenas con respecto al nombre del usuario, el identificador de usuario y un diccionario definido por la aplicación.  Además, trate los caracteres visualmente similares como equivalentes al realizar las comparaciones.  Por ejemplo, considere las letras "l" y "e" como equivalentes a los números "1" y "3".  
  
-   Si hay sólo un carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.  
  
-   Asegúrese de que los últimos dos caracteres de la contraseña son caracteres de letra.  
  
-   No permita contraseñas en las que todos los símbolos se escriben desde la fila superior del teclado.  
  
## Vea también  
 <xref:System.Text.RegularExpressions.Regex>   
 [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md)