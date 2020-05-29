---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206228"
---
### <a name="resource-manifest-file-name-change"></a>Cambio de nombre de archivo de manifiesto del recurso

A partir de .NET Core 3.0, en el caso predeterminado, MSBuild genera un nombre de archivo de manifiesto diferente para los archivos de recursos.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="change-description"></a>Descripción del cambio

Antes de .NET Core 3.0, si no se especificaban los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento de `EmbeddedResource` del archivo del proyecto, MSBuild generaba un nombre de archivo de manifiesto con el patrón `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`. Si `RootNamespace` no está definido en el archivo del proyecto, se toma como valor predeterminado el nombre del proyecto. Por ejemplo, el nombre de manifiesto generado para un archivo de recursos denominado *Form1.resx* en el directorio raíz del proyecto era *suproject.Form1.Resources*.

A partir de .NET Core 3.0, si un archivo de recursos está ubicado conjuntamente con un archivo de código fuente del mismo nombre (por ejemplo, *Form1.resx* y *Form1.cs*), MSBuild usa la información de tipo del archivo de código fuente para generar el nombre del archivo de manifiesto con el patrón `<Namespace>.<ClassName>.resources`. El espacio de nombres y el nombre de clase se extraen del primer tipo del archivo de código fuente ubicado conjuntamente. Por ejemplo, el nombre de manifiesto generado para un archivo de recursos denominado *Form1.resx* que se ubica conjuntamente con un archivo de código fuente denominado *Form1.cs* es *myNameSpace.Form1.Resources*. Lo más importante que hay que tener en cuenta es que la primera parte del nombre de archivo es diferente en versiones anteriores de .NET Core (*myNameSpace* en lugar de *MyProject*).

> [!NOTE]
> Si tiene los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` especificados en un elemento `EmbeddedResource` del archivo del proyecto, este cambio no afecta a ese archivo de recursos.

Este cambio importante se presentó con la incorporación de la propiedad `EmbeddedResourceUseDependentUponConvention` a los proyectos de .NET Core. De forma predeterminada, los archivos de recursos no se enumeran explícitamente en un archivo de proyecto de .NET Core, por lo que no tienen metadatos `DependentUpon` para especificar cómo nombrar el archivo *.resources* generado. Cuando `EmbeddedResourceUseDependentUponConvention` se establece en `true`, que es el valor predeterminado, MSBuild busca un archivo de código fuente ubicado conjuntamente y extrae un espacio de nombres y un nombre de clase de ese archivo. Si establece `EmbeddedResourceUseDependentUponConvention` en `false`, MSBuild genera el nombre del manifiesto según el comportamiento anterior, que combina `RootNamespace` y la ruta de acceso relativa del archivo.

#### <a name="recommended-action"></a>Acción recomendada

En la mayoría de los casos, no se requiere ninguna acción por parte del desarrollador y la aplicación seguirá funcionando. Sin embargo, si este cambio invalida la aplicación, puede:

- Cambiar el código para que espere el nuevo nombre de manifiesto.

- Rechazar la nueva convención de nomenclatura mediante el establecimiento de `EmbeddedResourceUseDependentUponConvention` en `false` en el archivo del proyecto.

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D
