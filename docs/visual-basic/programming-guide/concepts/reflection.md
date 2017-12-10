---
title: "Reflexión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2ae87eae971129059a7e84b36971c13a5fe71b
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="reflection-visual-basic"></a>Reflexión (Visual Basic)
La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos. Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades. Si usa atributos en el código, la reflexión le permite acceder a ellos. Para obtener más información, consulte [Attributes](../../../../docs/standard/attributes/index.md) (Atributos).  
  
 Este es un ejemplo simple de reflexión que usa el método estático `GetType`, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 El resultado es el siguiente:  
  
 `System.Int32`  
  
 En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 El resultado es el siguiente:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Información general de la reflexión  
 La reflexión resulta útil en las siguientes situaciones:  
  
-   Cuando tenga que acceder a atributos en los metadatos del programa. Para obtener más información, consulte [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos).  
  
-   Para examinar y crear instancias de tipos en un ensamblado.  
  
-   Para generar nuevos tipos en tiempo de ejecución. Usar clases en <xref:System.Reflection.Emit>.  
  
-   Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución. Consulte el tema [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Reflexión](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [Viewing Type Information](../../../framework/reflection-and-codedom/viewing-type-information.md) (Ver información tipos)  
  
-   [Reflection and Generic Types](../../../framework/reflection-and-codedom/reflection-and-generic-types.md) (Reflexión y tipos genéricos)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)  
 [Ensamblados en Common Language Runtime](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
