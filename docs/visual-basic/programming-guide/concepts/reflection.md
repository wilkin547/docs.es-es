---
title: "Reflexión (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ae042933575849e105d7b681634a61319c1d6ee
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-visual-basic"></a>Reflexión (Visual Basic)
La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos.</xref:System.Type> Puede usar la reflexión para dinámicamente crea una instancia de un tipo, enlazar el tipo a un objeto existente, obtener el tipo de un objeto existente e invocar sus métodos o tener acceso a sus campos y propiedades. Si utiliza atributos en el código, la reflexión permite tener acceso a ellos. Para obtener más información, consulte [atributos](https://msdn.microsoft.com/library/5x6cd29c).  
  
 Este es un ejemplo simple de reflexión que utiliza el método estático `GetType` , heredada por todos los tipos de la `Object` clase - para obtener el tipo de una variable de base:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 El resultado es:  
  
 `System.Int32`  
  
 En el ejemplo siguiente se utiliza la reflexión para obtener el nombre completo del ensamblado cargado.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 El resultado es:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Información general de la reflexión  
 La reflexión resulta útil en las situaciones siguientes:  
  
-   Cuando tenga que obtener acceso a atributos en los metadatos del programa. Para obtener más información, consulte [recuperar información almacenada en atributos](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).  
  
-   Para examinar y crear instancias de tipos en un ensamblado.  
  
-   Para generar nuevos tipos en tiempo de ejecución. Usar las clases en <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit>  
  
-   Para realizar el enlace, acceso a métodos en tipos creados en tiempo de ejecución. Vea el tema [cargar y utilizar tipos dinámicamente](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Reflexión](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [Ver información de tipos](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [Reflexión y tipos genéricos](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit></xref:System.Reflection.Emit>  
  
-   [Recuperar información almacenada en atributos](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de Visual Basic](../../../visual-basic/programming-guide/index.md)   
 [Ensamblados en Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)
