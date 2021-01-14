---
title: Cómo genera MSBuild los nombres de archivo de manifiesto
description: Describe los factores que influyen en el nombre de un archivo de manifiesto de recurso generado por MSBuild en tiempo de compilación.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866394"
---
# <a name="how-resource-manifest-files-are-named"></a>Cómo se asigna un nombre a los archivos de manifiesto del recurso

Cuando MSBuild compila un proyecto de .NET Core, los archivos de recursos XML, que tienen la extensión de archivo *.resx*, se convierten en archivos *.resources* binarios. Los archivos binarios se insertan en la salida del compilador y los puede leer el <xref:System.Resources.ResourceManager>. En este artículo se describe cómo MSBuild elige un nombre para cada archivo *.resources*.

> [!TIP]
> Si agrega explícitamente un elemento de recurso al archivo de proyecto y también se [incluye con los patrones globales de inclusión predeterminados para .NET Core](../project-sdk/overview.md#default-compilation-includes), obtendrá un error de compilación. Para incluir manualmente los archivos de recursos como elementos `EmbeddedResource`, establezca la propiedad `EnableDefaultEmbeddedResourceItems` en false.

## <a name="default-name"></a>Nombre predeterminado

En .NET Core 3.0 y versiones posteriores, se usa el nombre predeterminado de un manifiesto del recurso cuando se cumplen las dos condiciones siguientes:

- El archivo de recursos no se incluye de forma explícita en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon`.
- La propiedad `EmbeddedResourceUseDependentUponConvention` no se ha establecido en `false` en el archivo del proyecto. De manera predeterminada, esta propiedad está establecida en `true`. Para obtener más información, vea [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).

Si el archivo de recursos está ubicado con un archivo de origen ( *.cs* o *.vb*) del mismo nombre de archivo raíz, se usa el nombre completo del primer tipo que se define en el archivo de origen para el nombre de archivo de manifiesto. Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, y *Form1.cs* se ubica conjuntamente con *Form1.resx*, el nombre de manifiesto generado para ese archivo de recursos es *MyNameSpace.Form1.resources*.

## <a name="logicalname-metadata"></a>Metadatos LogicalName

Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `LogicalName`, se usa el valor `LogicalName` como nombre de manifiesto. `LogicalName` tiene prioridad sobre cualquier otro metadato o configuración.

Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

O bien

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a>Metadatos ManifestResourceName

Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `ManifestResourceName` (y `LogicalName` no está presente), se usa el valor `ManifestResourceName` combinado con la extensión de archivo *.resources* como nombre de archivo de manifiesto.

Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.resources*.

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

El nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.fr-FR.resources*.

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a>Metadatos DependentUpon

Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `DependentUpon` (y `LogicalName` y `ManifestResourceName` no están presentes), se usa la información del archivo de origen definido por `DependentUpon` para el nombre de archivo de manifiesto del recurso. Específicamente, el nombre del primer tipo que se define en el archivo de código fuente se usa en el nombre del manifiesto como se indica a continuación: *Namespace.Classname\[.Culture].resources*.

Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *Namespace.Classname.resources* (donde `Namespace.Classname` es la primera clase que se define en *MyTypes.cs*).

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

El nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es la primera clase que se define en *MyTypes.cs*).

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a>EmbeddedResourceUseDependentUponConvention property

Si `EmbeddedResourceUseDependentUponConvention` se establece en`false` en el archivo de proyecto, cada nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa desde la raíz del proyecto al archivo *.resx*. Más específicamente, el nombre de archivo de manifiesto del recurso generado es *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. Esta es también la lógica que se usa para generar nombres de manifiesto en versiones de .NET Core anteriores a la 3.0.

> [!NOTE]
>
> - Si `RootNamespace` no está definido, se toma como valor predeterminado el nombre del proyecto.
> - Si se especifican metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource` del archivo de proyecto, esta regla de nomenclatura no se aplica a ese archivo de recursos.

## <a name="see-also"></a>Consulte también

- [Funcionamiento de la nomenclatura del recurso del manifiesto](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [Propiedades de MSBuild para proyectos del SDK de .NET Core](../project-sdk/msbuild-props.md)
- [Cambios importantes de MSBuild](../compatibility/msbuild.md)
