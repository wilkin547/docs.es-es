---
title: 'Algoritmo de carga de ensamblado satélite: .NET Core'
description: Descripción de los detalles del algoritmo de carga de ensamblado satélite en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 17f29a9aca79019daa91736e586bf1b6b753a9ec
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859534"
---
# <a name="satellite-assembly-loading-algorithm"></a>Algoritmo de carga de ensamblado satélite

Los ensamblados satélite se utilizan con el fin de almacenar los recursos localizados personalizados para el idioma y la referencia cultural.

Los ensamblados satélite usan un algoritmo de carga distinto al de los ensamblados administrados generales.

## <a name="when-are-satellite-assemblies-loaded"></a>¿Cuándo se cargan los ensamblados satélite?

Los ensamblados satélite se cargan al cargar un recurso localizado.

La API básica para cargar recursos localizados es la clase <xref:System.Resources.ResourceManager?displayProperty=fullName>. En última instancia, la clase <xref:System.Resources.ResourceManager> llamará al método <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> para cada <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.

Las API de nivel alto pueden abstraer la API de nivel bajo.

## <a name="algorithm"></a>Algoritmo

El proceso de reserva de recursos de .NET Core conlleva los pasos siguientes:

1. Determine la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> `active`. En todos los casos, la instancia de `active` es el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> del ensamblado que se ejecuta.

2. La instancia de `active` intenta cargar un ensamblado satélite para la referencia cultural solicitada por orden de prioridad al realizar lo siguiente:
    - Comprobar la memoria caché.
    - Comprobar en el directorio del ensamblado actualmente en ejecución un subdirectorio que coincida con el elemento <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> solicitado (por ejemplo, `es-MX`).

        > [!NOTE]
        > Esta característica no se ha implementado en .NET Core antes de la versión 3.0.
        >
        > [!NOTE]
        > En Linux y macOS, el subdirectorio distingue entre mayúsculas y minúsculas y debe cumplir lo siguiente:
        >
        > - Coincidir exactamente con mayúsculas y minúsculas.
        > - Estar en minúsculas.

    - Si `active` es la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, ejecutar la lógica [sondeo del ensamblado de satélite (recurso) predeterminado](default-probing.md#satellite-resource-assembly-probing).

    - Llamar a la función de <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.

    - Generar el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>.

    - Generar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

3. Si se carga un ensamblado satélite:
   - Se genera el evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Se busca en el ensamblado el recurso solicitado. Si el runtime encuentra el recurso en el ensamblado, lo usará. Si no encuentra el recurso, seguirá con la búsqueda.

    > [!NOTE]
    > Para buscar un recurso dentro del ensamblado satélite, el entorno de ejecución busca el archivo de recursos solicitado por <xref:System.Resources.ResourceManager> para el <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> actual. En el archivo de recursos, busca el nombre del recurso solicitado. Si no se encuentra ninguno, se considera que no se encontró el recurso.

4. Luego, el runtime busca los ensamblados de referencias culturales primarias a través de muchos niveles potenciales, y cada vez repite los pasos 2 y 3.

    Cada referencia cultural tiene solo un elemento primario, que está definido mediante la propiedad <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>.

    La búsqueda de las referencias culturales primarias se detiene cuando la propiedad <xref:System.Globalization.CultureInfo.Parent%2A> de una referencia cultural es <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

    En el caso de <xref:System.Globalization.CultureInfo.InvariantCulture>, no se vuelve a los pasos 2 y 3, sino que continúa con el paso 5.

5. Si todavía no se encuentra el recurso, se usa el recurso para la referencia cultural predeterminada (de reserva).

   Normalmente, los recursos de la referencia cultural predeterminada se incluyen en el ensamblado de la aplicación principal. Sin embargo, se puede especificar <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> para la propiedad <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>. Este valor indica que la ubicación de reserva final para los recursos es un ensamblado satélite, en lugar del ensamblado principal.

    > [!NOTE]
    > La referencia cultural predeterminada es la reserva final. Por lo tanto, se recomienda incluir siempre un conjunto de recursos exhaustivo en el archivo de recursos predeterminado. Esto ayuda a evitar que se produzcan excepciones. Al tener un conjunto exhaustivo, se proporciona una reserva para todos los recursos y se garantiza que al menos un recurso esté siempre presente para el usuario, incluso si no es específico de la referencia cultural.

6. Por último,
   - si el tiempo de ejecución no encuentra un archivo de recursos para una referencia cultural predeterminada (de reserva), se produce una excepción <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException>.
   - Si se encuentra el archivo de recursos pero el recurso solicitado no se encuentra, la solicitud devuelve `null`.
