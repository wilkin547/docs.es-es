---
title: Procedimiento Inspección del contenido de un ensamblado con MetadataLoadContext
description: Aprenda a usar MetadataLoadContext, que es una API que le permite cargar ensamblados .NET con fines de inspección.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 90c84147c52199afc42a2efc297bc7fe40658ec7
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141203"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>Procedimiento Inspección del contenido de un ensamblado con MetadataLoadContext

De forma predeterminada, la API de reflexión de .NET permite a los desarrolladores inspeccionar el contenido de los ensamblados cargados en el contexto de ejecución principal. Sin embargo, a veces no es posible cargar un ensamblado en el contexto de ejecución, por ejemplo, porque se compiló para otra arquitectura de procesador o plataforma, o es un [ensamblado de referencia](reference-assemblies.md). La API de <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName> permite cargar e inspeccionar dichos ensamblados. Los ensamblados cargados en <xref:System.Reflection.MetadataLoadContext> se tratan únicamente como metadatos, es decir, se pueden examinar los tipos del ensamblado, pero no se puede ejecutar ningún código que contenga. A diferencia del contexto de ejecución principal, <xref:System.Reflection.MetadataLoadContext> no carga automáticamente las dependencias del directorio actual, sino que usa la lógica de enlace personalizada proporcionada por la clase <xref:System.Reflection.MetadataAssemblyResolver> que se le ha pasado.

## <a name="prerequisites"></a>Requisitos previos

Para usar <xref:System.Reflection.MetadataLoadContext>, instale el paquete NuGet [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Se admite en cualquier plataforma de destino compatible con .NET Standard 2.0, por ejemplo, .NET Core 2.0 o .NET Framework 4.6.1.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>Creación de MetadataAssemblyResolver para MetadataLoadContext

Para crear la clase <xref:System.Reflection.MetadataLoadContext> es necesario proporcionar la instancia de la clase <xref:System.Reflection.MetadataAssemblyResolver>. La manera más sencilla de proporcionar una es usar la clase <xref:System.Reflection.PathAssemblyResolver>, que resuelve los ensamblados de la colección especificada de cadenas de ruta de acceso de ensamblado. Esta colección, además de los ensamblados que quiere inspeccionar directamente, también debe incluir todas las dependencias necesarias. Por ejemplo, para leer el atributo personalizado que se encuentra en un ensamblado externo, debe incluir ese ensamblado o se producirá una excepción. En la mayoría de los casos, debe incluir al menos el *ensamblado principal*, es decir, el ensamblado que contiene tipos de sistema integrados, como <xref:System.Object?displayProperty=nameWithType>. En el código siguiente se muestra cómo crear la clase <xref:System.Reflection.PathAssemblyResolver> mediante la colección que consta del ensamblado inspeccionado y el ensamblado principal del entorno de ejecución actual:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

Si necesita tener acceso a todos los tipos de BCL, puede incluir todos los ensamblados en tiempo de ejecución de la colección. En el código siguiente se muestra cómo crear la clase <xref:System.Reflection.PathAssemblyResolver> mediante la colección que consta del ensamblado inspeccionado y todos los ensamblados del entorno de ejecución actual:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>Creación de MetadataLoadContext

Para crear la clase <xref:System.Reflection.MetadataLoadContext>, invoque su constructor <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29>, y pase la clase <xref:System.Reflection.MetadataAssemblyResolver> creada previamente como primer parámetro y el nombre del ensamblado principal como segundo parámetro. Puede omitir el nombre del ensamblado principal, en cuyo caso el constructor intentará usar nombres predeterminados: "mscorlib", "System.Runtime" o "netstandard".

Después de crear el contexto, puede cargar los ensamblados en él mediante métodos como <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A>. Puede usar todas las API de reflexión en los ensamblados cargados, excepto las que tienen que ver con la ejecución de código. El método <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A> supone la ejecución de constructores, así que use el método <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A> en su lugar cuando necesite examinar los atributos personalizados de la clase <xref:System.Reflection.MetadataLoadContext>.

En el siguiente ejemplo de código se crea la clase <xref:System.Reflection.MetadataLoadContext>, se carga en ella el ensamblado y se generan los atributos del ensamblado en la consola:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>Ejemplo

Para obtener un ejemplo de código completo, vea el [ejemplo Inspección del contenido de un ensamblado mediante MetadataLoadContext](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/).
