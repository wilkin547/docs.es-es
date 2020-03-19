---
title: 'Algoritmo de carga de ensamblado administrado: .NET Core'
description: Descripción de los detalles del algoritmo de carga de ensamblado administrado en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973508"
---
# <a name="managed-assembly-loading-algorithm"></a>Algoritmo de carga de ensamblado administrado

Los ensamblados administrados se ubican y se cargan con un algoritmo que implica varias fases.

Todos los ensamblados administrados, excepto los ensamblados satélite y los de `WinRT`, usan el mismo algoritmo.

## <a name="when-are-managed-assemblies-loaded"></a>¿Cuándo se cargan los ensamblados administrados?

El mecanismo más común para desencadenar la carga de un ensamblado administrado es una referencia estática de ensamblado. El compilador inserta estas referencias siempre que el código usa un tipo definido en otro ensamblado. Estos ensamblados los carga (`load-by-name`) el runtime, según sea necesario.

El uso directo de API específicas también desencadenará cargas:

|API  |Descripción  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|La instancia de [this](../../csharp/language-reference/keywords/this.md).|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Cargue desde la ruta de acceso.|La instancia de [this](../../csharp/language-reference/keywords/this.md).|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Cargue desde el objeto.|La instancia de [this](../../csharp/language-reference/keywords/this.md).|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Cargue desde la ruta de acceso en una nueva instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>.|La nueva instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Cargue desde la ruta de acceso en la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.<p>Agregue un controlador <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> a <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>. El controlador cargará las dependencias del ensamblado desde su directorio.|Instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|Se infiere del autor de la llamada.<p>Prefiere los métodos <xref:System.Runtime.Loader.AssemblyLoadContext>.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Cargue desde el objeto en una nueva instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>.|La nueva instancia de <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`.|Se infiere del autor de la llamada.<p>Prefiere los métodos <xref:System.Type.GetType%2A?displayProperty=nameWithType> con un argumento `assemblyResolver`.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Si el tipo `name` describe un tipo genérico calificado con el ensamblado, desencadene un elemento `Load-by-name`.|Se infiere del autor de la llamada.<p>Prefiere <xref:System.Type.GetType%2A?displayProperty=nameWithType> al utilizar nombres de tipo calificados con el ensamblado.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`.|Se infiere del autor de la llamada.<p>Prefiere los métodos <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que toman un argumento <xref:System.Type>.|

## <a name="algorithm"></a>Algoritmo

El algoritmo siguiente describe cómo el runtime carga un ensamblado administrado.

1. Determine el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`.

    - En el caso de una referencia estática de ensamblado, el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active` es la instancia que ha cargado el ensamblado de referencia.
    - Las API preferidas hacen que el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active` sea explícito.
    - Otras API infieren el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`. Para estas API, se usa la propiedad <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType>. Si su valor es `null`, se usa la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> inferida.
    - Consulte la tabla anterior.

2. En el caso de los métodos `Load-by-name`, el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> activo carga el ensamblado. En orden de prioridad por:
    - Comprobar su `cache-by-name`.

    - Llamar a la función de <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.

    - Comprobar la memoria caché de las instancias de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> y ejecutar la lógica [sondeo predeterminado de ensamblado administrado](default-probing.md#managed-assembly-default-probing).

    - Generar el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> para el AssemblyLoadContext activo.

    - Generar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

3. En los demás tipos de cargas, el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active` carga el ensamblado. En orden de prioridad por:
    - Comprobar su `cache-by-name`.

    - Cargar desde la ruta de acceso especificada o el objeto de ensamblado sin formato.

4. En cualquier caso, si se ha cargado un ensamblado recientemente, entonces ocurre lo siguiente:
   - Se genera el evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Se agrega una referencia al elemento `cache-by-name` de la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> del ensamblado.

5. Si se encuentra el ensamblado, se agrega una referencia según sea necesario al elemento `cache-by-name` de la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> `active`.
