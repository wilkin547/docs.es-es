---
title: Opciones de recorte
description: Obtenga información sobre cómo controlar el recorte de aplicaciones autocontenidas.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 93fee991cf218a52ad1d9a2597b1c9b2d442110a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874256"
---
# <a name="trimming-options"></a>Opciones de recorte

Los siguientes elementos y propiedades de MSBuild influyen en el comportamiento de [implementaciones autocontenidas recortadas](trim-self-contained.md). Algunas de las opciones mencionan `ILLink`, que es el nombre de la herramienta subyacente que implementa el recorte. Puede encontrar más información sobre la herramienta subyacente en la [documentación del enlazador](https://github.com/mono/linker/tree/master/docs).

## <a name="enable-trimming"></a>Habilitación del recorte

- `<PublishTrimmed>true</PublishTrimmed>`

   Habilite el recorte durante la publicación, con la configuración predeterminada definida por el SDK.

Al usar `Microsoft.NET.Sdk`, se realizará un recorte en el nivel de ensamblado de los ensamblados de marco en el paquete del entorno de ejecución de netcoreapp. El código de aplicación y las bibliotecas que no son del marco no se recortan. Otros SDK pueden definir diferentes valores predeterminados.

## <a name="trimming-granularity"></a>Granularidad del recorte

La siguiente configuración de granularidad controla la agresividad con la que se descarta el IL sin usar. Se puede establecer como una propiedad o como metadatos en un [ensamblado individual](#trimmed-assemblies).

- `<TrimMode>copyused</TrimMode>`

   Habilite el recorte en el nivel de ensamblado, lo que mantendrá un ensamblado completo si se usa cualquier parte de este (de manera estática).

- `<TrimMode>link</TrimMode>`

    Habilite el recorte a nivel de miembro, lo que quita los miembros sin usar de los tipos.

Los ensamblados con metadatos de `<IsTrimmable>true</IsTrimmable>`, pero sin un valor de `TrimMode` explícito, usarán el valor global de `TrimMode`. El valor predeterminado de `TrimMode` para `Microsoft.NET.Sdk` es `copyused`.

## <a name="trimmed-assemblies"></a>Ensamblados recortados

Al publicar una aplicación recortada, el SDK calcula un elemento `ItemGroup` llamado `ManagedAssemblyToLink` que representa el conjunto de archivos que se va a procesar para el recorte. `ManagedAssemblyToLink` puede tener metadatos que controlan el comportamiento de recorte por ensamblado. Para establecer estos metadatos, cree un destino que se ejecute antes del destino `PrepareForILLink` integrado. En el ejemplo siguiente se muestra cómo habilitar el recorte de `MyAssembly`.

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

No agregue ni quite elementos de `ManagedAssemblyToLink`, porque el SDK procesa este conjunto durante la publicación y espera que no cambie. Los metadatos admitidos son:

- `<IsTrimmable>true</IsTrimmable>`

  Controle si se ha recortado el ensamblado especificado.

- `<TrimMode>copyused</TrimMode>` o `<TrimMode>link</TrimMode>`

  Controle la [granularidad del recorte](#trimming-granularity) de este ensamblado. Esto tiene prioridad sobre el valor global de `TrimMode`. La configuración del valor `TrimMode` en un ensamblado implica `<IsTrimmable>true</IsTrimmable>`.

## <a name="root-assemblies"></a>Ensamblados raíz

Todos los ensamblados que no tienen `<IsTrimmable>true</IsTrimmable>` se consideran raíces para el análisis, lo que significa que se conservarán todas sus dependencias estáticas. Se pueden "enraizar" ensamblados adicionales por nombre (sin la extensión `.dll`):

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a>Descriptores raíz

Otra manera de especificar las raíces para el análisis consiste en usar un archivo XML que use el [formato de descriptor](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format) del enlazador. Esto le permite enraizar miembros específicos en lugar de un ensamblado completo.

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

Por ejemplo, `MyRoots.xml` podría enraizar un método específico al que la aplicación tiene acceso dinámicamente:

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a>Advertencias de análisis

El recorte quitará el IL que no es accesible estáticamente. Las aplicaciones que usan reflexión u otros patrones que crean dependencias dinámicas pueden romperse mediante el recorte. Para advertir sobre tales patrones:

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    Habilite las advertencias de análisis de recorte.

Esto incluirá advertencias sobre toda la aplicación, incluidas las de su propio código, del código de la biblioteca y del código del marco.

## <a name="warning-versions"></a>Versiones de advertencias

El análisis de recorte respeta la propiedad [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) que controla la versión de las advertencias de análisis en el SDK. Hay otra propiedad que controla la versión de las advertencias de análisis de recorte de forma independiente (similar a `WarningLevel` para el compilador):

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    Emita solo advertencias del nivel especificado o de uno inferior. Puede ser `9999` para incluir todas las versiones de advertencias.

## <a name="suppressing-warnings"></a>Supresión de advertencias

Los [códigos de advertencia](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) individuales se pueden suprimir mediante las propiedades de MSBuild habituales que respeta la cadena de herramientas, incluidas `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` y `TreatWarningsAsErrors`. Existe una opción adicional que controla el comportamiento de advertencia como error de ILLink de forma independiente:

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    No trate las advertencias de ILLink como errores. Esto puede ser útil para evitar convertir advertencias de análisis de recorte en errores cuando se tratan las advertencias del compilador como errores globalmente.

## <a name="removing-symbols"></a>Eliminación de símbolos

Normalmente, los símbolos se recortan para que coincidan con los ensamblados recortados. También puede quitar todos los símbolos:

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    Quite los símbolos de la aplicación recortada, incluidos los archivos PDB incrustados y los archivos PDB independientes. Esto se aplica tanto al código de la aplicación como a las dependencias de los símbolos.

El SDK también permite deshabilitar la compatibilidad del depurador con la propiedad `DebuggerSupport`. Cuando la compatibilidad con el depurador está deshabilitada, el recorte quitará los símbolos automáticamente (el valor predeterminado de `TrimmerRemoveSymbols` se establece en "true").

## <a name="trimming-framework-library-features"></a>Características de recorte de las bibliotecas de marco

Varias áreas de características de las bibliotecas de marco incluyen directivas de enlazador que permiten eliminar el código de las características deshabilitadas.

- `<DebuggerSupport>false</DebuggerSupport>`

    Elimina código que permite mejores experiencias de depuración. También [elimina los símbolos](#removing-symbols).

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    Elimina la compatibilidad con la serialización BinaryFormatter. Para obtener más información, consulte la sección [Métodos de serialización BinaryFormatter obsoletos](../compatibility/core-libraries/5.0/binaryformatter-serialization-obsolete.md).

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    Elimina el código de codificación UTF-7 poco seguro. Para obtener más información, vea la sección [Rutas de acceso al código UTF-7 obsoletas](../compatibility/core-libraries/5.0/utf-7-code-paths-obsolete.md).

- `<EventSourceSupport>false</EventSourceSupport>`

    Elimina el código o la lógica relacionados con EventSource.

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    Elimina el código relacionado con la compatibilidad de diagnóstico para System.Net.Http.

- `<InvariantGlobalization>true</InvariantGlobalization>`

    Elimina el código y los datos específicos de la globalización. Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    Elimina los mensajes de excepción para los ensamblados de `System.*`. Cuando un ensamblado de `System.*` produzca una excepción, el mensaje será un identificador de recurso simplificado en lugar del mensaje completo.

 Estas propiedades harán que el código relacionado se recorte y también deshabilitarán las características a través del archivo [runtimeconfig](../run-time-config/index.md). Para obtener más información sobre estas propiedades, incluidas las opciones de runtimeconfig correspondientes, vea la página sobre [modificadores de características](https://github.com/dotnet/runtime/blob/main/docs/workflow/trimming/feature-switches.md). Algunos SDK pueden tener valores predeterminados para estas propiedades.
