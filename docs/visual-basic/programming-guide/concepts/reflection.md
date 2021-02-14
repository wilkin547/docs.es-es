---
description: 'Más información acerca de: reflexión (Visual Basic)'
title: Reflexión
ms.date: 07/20/2015
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
ms.openlocfilehash: 532087f2ac32242b473d4524a6026519951d96d2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486815"
---
# <a name="reflection-visual-basic"></a>Reflection (Visual Basic) (Reflexión [Visual Basic])

La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos. Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades. Si usa atributos en el código, la reflexión le permite acceder a ellos. Para obtener más información, consulte [Attributes](../../../standard/attributes/index.md) (Atributos).  
  
 Este es un ejemplo simple de reflexión que usa el método estático `GetType`, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 La salida es la siguiente:  
  
 `System.Int32`  
  
 En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 La salida es la siguiente:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Información general de la reflexión  

 La reflexión resulta útil en las siguientes situaciones:  
  
- Cuando tenga que acceder a atributos en los metadatos del programa. Para obtener más información, consulte [Recuperar información almacenada en atributos](../../../standard/attributes/retrieving-information-stored-in-attributes.md).  
  
- Para examinar y crear instancias de tipos en un ensamblado.  
  
- Para generar nuevos tipos en tiempo de ejecución. Usar clases en <xref:System.Reflection.Emit>.  
  
- Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución. Consulte el tema [Cargar y utilizar tipos dinámicamente](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
## <a name="related-sections"></a>Secciones relacionadas  

 Para obtener más información:  
  
- [Reflexión](../../../framework/reflection-and-codedom/reflection.md)  
  
- [Ver información tipos](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
- [Reflexión y tipos genéricos](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
- <xref:System.Reflection.Emit>  
  
- [Recuperar la información almacenada en atributos](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación en Visual Basic](../index.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
