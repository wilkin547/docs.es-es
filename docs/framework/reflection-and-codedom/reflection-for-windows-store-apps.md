---
title: Reflexión en .NET Framework para aplicaciones de la Tienda Windows
description: Use la reflexión de .NET para aplicaciones de la Tienda Windows. Hay un conjunto de tipos y miembros de reflexión que se pueden usar en las aplicaciones de la Tienda Windows, que están disponibles para la totalidad de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection, Windows Store apps
- .NET for Windows Store apps, TypeInfo class
ms.assetid: 0d07090c-9b47-4ecc-81d1-29d539603c9b
ms.openlocfilehash: dd92696fdbe534c549b3aba25533533280485cfe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263417"
---
# <a name="reflection-in-the-net-framework-for-windows-store-apps"></a>Reflexión en .NET Framework para aplicaciones de la Tienda Windows

A partir de .NET Framework 4.5, .NET Framework incluye un conjunto de tipos y miembros de reflexión para su uso en aplicaciones de la Tienda Windows 8.x. Estos tipos y miembros están disponibles en la versión completa de .NET Framework, así como en las aplicaciones .NET para la Tienda Windows. En este documento se explican las diferencias principales entre estos y sus homólogos en .NET Framework 4 y versiones anteriores.  
  
 Si va a crear una aplicación de la Tienda Windows 8.x, debe usar los tipos y miembros de reflexión de las aplicaciones .NET para la Tienda Windows 8.x. Estos tipos y miembros también están disponibles, aunque no son necesarios, para su uso en aplicaciones de escritorio, por lo que puede usar el mismo código para ambos tipos de aplicaciones.  
  
## <a name="typeinfo-and-assembly-loading"></a>TypeInfo y carga de ensamblados  

 En las aplicaciones .NET para la Tienda Windows 8.x, la clase <xref:System.Reflection.TypeInfo> contiene algunas funcionalidades de la clase <xref:System.Type> de .NET Framework 4. Un objeto <xref:System.Type> representa una referencia a una definición de tipo, mientras que un objeto <xref:System.Reflection.TypeInfo> representa la propia definición de tipo. Esto permite manipular los objetos <xref:System.Type> sin necesidad de que el runtime cargue el ensamblado al que hacen referencia. Al obtener el objeto <xref:System.Reflection.TypeInfo> asociado se fuerza la carga del ensamblado.  
  
 <xref:System.Reflection.TypeInfo> contiene muchos de los miembros disponibles en <xref:System.Type>, y muchas de las propiedades de reflexión de las aplicaciones .NET para la Tienda Windows 8.x devuelven colecciones de objetos <xref:System.Reflection.TypeInfo>. Para obtener un objeto <xref:System.Reflection.TypeInfo> a partir de un objeto <xref:System.Type>, use el método <xref:System.Reflection.IReflectableType.GetTypeInfo%2A>.  
  
## <a name="query-methods"></a>Métodos de consulta  

 En las aplicaciones .NET para la Tienda Windows 8.x, use las propiedades de reflexión que devuelven colecciones de <xref:System.Collections.Generic.IEnumerable%601> en lugar de los métodos que devuelven matrices. Los contextos de reflexión pueden implementar el recorrido diferido de estas colecciones para los ensamblados o tipos de gran tamaño.  
  
 Las propiedades de reflexión solo devuelven los métodos declarados en un objeto determinado en lugar de recorrer el árbol de herencia. Además, no usan los parámetros <xref:System.Reflection.BindingFlags> para el filtrado. En su lugar, el filtrado tiene lugar en el código de usuario, mediante el uso de consultas LINQ en las colecciones devueltas. Para los objetos de reflexión que se originan con el runtime (por ejemplo, como resultado de `typeof(Object)`), recorrer el árbol de herencia se logra mejor usando los métodos del asistente de la clase <xref:System.Reflection.RuntimeReflectionExtensions>. Los consumidores de objetos de contextos de reflexión personalizados no pueden usar estos métodos, y deben recorrer el árbol de herencia por su cuenta.  
  
## <a name="restrictions"></a>Restricciones  

 En una aplicación de la Tienda Windows 8.x, el acceso a algunos tipos y miembros de .NET Framework está restringido. Por ejemplo, no puede llamar a los métodos de .NET Framework que no estén incluidos en aplicaciones .NET para la Tienda Windows 8.x mediante un objeto <xref:System.Reflection.MethodInfo>. Además, ciertos tipos y miembros que no se consideran seguros en el contexto de una aplicación de la Tienda Windows 8.x están bloqueados, al igual que los miembros <xref:System.Runtime.InteropServices.Marshal> y <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal>. Esta restricción solo afecta a los tipos y miembros de .NET Framework; puede llamar a su propio código o al de otros fabricantes como lo haría normalmente.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usan los tipos y miembros de reflexión de las aplicaciones .NET para la Tienda Windows 8.x a fin de recuperar los métodos y las propiedades del tipo <xref:System.Globalization.Calendar>, incluidos los métodos y las propiedades heredados. Para ejecutar este código, péguelo en el archivo de código de una página de la Tienda Windows 8.x que contenga un control <xref:Windows.UI.Xaml.Controls.TextBlock?displayProperty=nameWithType> denominado `textblock1` en un proyecto denominado Reflexión. Si pega este código dentro de un proyecto con otro nombre, asegúrese de cambiar el nombre del espacio de nombres para que coincida con su proyecto.  
  
 [!code-csharp[System.ReflectionWinStoreApp#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflectionwinstoreapp/cs/mainpage.xaml.cs#1)]
 [!code-vb[System.ReflectionWinStoreApp#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflectionwinstoreapp/vb/mainpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Reflexión](reflection.md)
