---
title: "Introducci&#243;n a los gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], acerca de los genéricos"
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# Introducci&#243;n a los gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
Las clases y los métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera que sus homólogos no genéricos no pueden.  Los tipos genéricos se utilizan frecuentemente con las colecciones y los métodos que funcionan en ellas.  La versión 2.0 de la biblioteca de clases de .NET Framework proporciona un nuevo espacio de nombres, <xref:System.Collections.Generic>, que contiene varias clases nuevas de colección basadas en tipos genéricos.  Se recomienda que todas las aplicaciones destinadas a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 2.0 y versiones posteriores utilicen las nuevas clases de colección genéricas en lugar de sus homólogas no genéricas anteriores, como <xref:System.Collections.ArrayList>.  Para obtener más información, vea [Tipos genéricos en la biblioteca de clases de .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 Claro está que también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones generalizadas propias y diseñar modelos eficaces que tengan seguridad de tipos.  El ejemplo de código siguiente muestra una clase de lista vinculada genérica para propósitos de demostración.  \(En la mayoría de los casos, es aconsejable utilizar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases de .NET Framework en lugar de crear una propia.\) El parámetro de tipo `T` se emplea en diversas ubicaciones donde generalmente se utilizaría un tipo concreto para indicar el tipo del elemento almacenado en la lista.  Este parámetro se utiliza de las formas siguientes:  
  
-   Como tipo de un parámetro de método en el método `AddHead`.  
  
-   Como tipo de valor devuelto del método público `GetNext` y la propiedad `Data` en la clase anidada `Node`.  
  
-   Como tipo de datos de los miembros privados en la clase anidada.  
  
 Observe que T está disponible para la clase anidada `Node`.  Cuando se creen instancias de `GenericList<T>` con un tipo concreto, por ejemplo `GenericList<int>`, cada aparición de `T` se reemplazará por `int`.  
  
 [!code-cs[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 En el ejemplo de código siguiente se muestra cómo el código de cliente utiliza la clase genérica `GenericList<T>` para crear una lista de enteros.  Con sólo cambiar el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:  
  
 [!code-cs[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)