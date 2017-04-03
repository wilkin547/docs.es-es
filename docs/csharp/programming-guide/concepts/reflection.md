---
title: "Reflexión (C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ab40ab2258703670576084eccf7fd7e1b113d08d
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-c"></a>Reflexión (C#)
La reflexión proporciona objetos (de tipo <xref:System.Type>) que describen los ensamblados, módulos y tipos. Puede usar la reflexión para crear dinámicamente una instancia de un tipo, enlazar el tipo a un objeto existente u obtener el tipo desde un objeto existente e invocar sus métodos, o acceder a sus campos y propiedades. Si usa atributos en el código, la reflexión le permite acceder a ellos. Para obtener más información, consulte [Attributes](https://msdn.microsoft.com/library/5x6cd29c) (Atributos).  
  
 Este es un ejemplo simple de reflexión que usa el método estático `GetType`, heredado por todos los tipos de la clase base `Object`, para obtener el tipo de una variable:  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 El resultado es el siguiente:  
  
 `System.Int32`  
  
 En el ejemplo siguiente se usa la reflexión para obtener el nombre completo del ensamblado cargado.  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 El resultado es el siguiente:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  Las palabras clave de C# `protected` y `internal` no tienen ningún significado en IL y no se usan en las API de reflexión. Los términos correspondientes en IL son *Family* y *Assembly*. Para identificar un método `internal` mediante reflexión, use la propiedad <xref:System.Reflection.MethodBase.IsAssembly%2A>. Para identificar un método `protected internal`, use <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.  
  
## <a name="reflection-overview"></a>Información general de la reflexión  
 La reflexión resulta útil en las siguientes situaciones:  
  
-   Cuando tenga que acceder a atributos en los metadatos del programa. Para obtener más información, consulte [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) (Recuperar la información almacenada en atributos).  
  
-   Para examinar y crear instancias de tipos en un ensamblado.  
  
-   Para generar nuevos tipos en tiempo de ejecución. Use las clases de <xref:System.Reflection.Emit>.  
  
-   Para llevar a cabo métodos de acceso de enlace en tiempo de ejecución en tipos creados en tiempo de ejecución. Consulte el tema [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc) (Cargar y usar tipos dinámicamente).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Reflexión](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [Viewing Type Information](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2) (Ver información tipos)  
  
-   [Reflection and Generic Types](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de) (Reflexión y tipos genéricos)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) (Recuperar la información almacenada en atributos)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Ensamblados en Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)
