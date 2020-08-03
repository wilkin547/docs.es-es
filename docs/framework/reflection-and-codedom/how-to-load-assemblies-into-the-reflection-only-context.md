---
title: Procedimiento para cargar ensamblados en el contexto de solo reflexión
description: Vea un ejemplo de cómo cargar ensamblados en el contexto de solo reflexión de .NET. Examine ensamblados compilados para otras plataformas o versiones de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: 92f847f6c61ba39bf8621af6080baccfdabe514a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865078"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a>Procedimiento para cargar ensamblados en el contexto de solo reflexión

El contexto de carga de solo reflexión permite examinar ensamblados compilados para otras plataformas o para otras versiones de .NET Framework. El código cargado en este contexto solo se puede examinar; no se puede ejecutar. Esto significa que no se pueden crear objetos, porque no se pueden ejecutar constructores. Dado que no se puede ejecutar el código, las dependencias no se cargan automáticamente. Si necesita examinarlas, tiene que cargarlas manualmente.

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a>Para cargar un ensamblado en el contexto de carga de solo reflexión

1. Use la sobrecarga del método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> para cargar el ensamblado a partir de su nombre para mostrar, o el método <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> para cargar el ensamblado a partir de su ruta de acceso. Si el ensamblado es una imagen binaria, use la sobrecarga del método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.

    > [!NOTE]
    > No puede usar el contexto de solo reflexión para cargar una versión de mscorlib.dll desde una versión de .NET Framework que no sea la versión del contexto de ejecución.

2. Si el ensamblado tiene dependencias, el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> no las carga. Si necesita examinarlas, tiene que cargarlas manualmente.

3. Determine si un ensamblado se carga en el contexto de solo reflexión mediante la propiedad <xref:System.Reflection.Assembly.ReflectionOnly%2A> del ensamblado.

4. Si se han aplicado atributos al ensamblado o a tipos del ensamblado, examine esos atributos mediante la clase <xref:System.Reflection.CustomAttributeData> para asegurarse de que no se realice ningún intento de ejecutar código en el contexto de solo reflexión. Use la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> para obtener objetos <xref:System.Reflection.CustomAttributeData> que representen a los atributos aplicados a un ensamblado, miembro, módulo o parámetro.

    > [!NOTE]
    > Los atributos aplicados al ensamblado o a su contenido podrían definirse en el ensamblado o en otro ensamblado cargado en el contexto de solo reflexión. No hay forma de saber de antemano dónde se definen los atributos.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra cómo examinar los atributos aplicados a un ensamblado cargado en el contexto de solo reflexión.

El ejemplo de código define un atributo personalizado con dos constructores y una propiedad. El atributo se aplica al ensamblado, a un tipo declarado en el ensamblado, a un método del tipo y a un parámetro del método. Cuando se ejecuta, el ensamblado se carga automáticamente en el contexto de solo reflexión y muestra información sobre los atributos personalizados que se le aplicaron a él y a los tipos y miembros que contiene.

> [!NOTE]
> Para simplificar el ejemplo de código, el ensamblado se carga y examina automáticamente. Normalmente no se esperaría encontrar el mismo ensamblado cargado tanto en el contexto de ejecución como en el contexto de solo reflexión.

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
