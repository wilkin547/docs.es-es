---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78967979"
---
### <a name="resource-manifest-file-names"></a>Nombres de archivo de manifiesto del recurso

A partir de .NET Core 3.0, ha cambiado el nombre del archivo de manifiesto del recurso generado.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="change-description"></a>Descripción del cambio

Antes de .NET Core 3.0, cuando se establecían los metadatos [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) de un archivo de recursos ( *.resx*) en el archivo del proyecto de MSBuild, el nombre generado del manifiesto era *Namespace.ClassName.Resources*. Si no se establecía [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile), el nombre generado del manifiesto era *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.

A partir de .NET Core 3.0, si un archivo *.resx* está en la misma ubicación que un archivo de origen que tiene el mismo nombre (por ejemplo, en las aplicaciones de Windows Forms), el nombre de manifiesto del recurso se genera a partir del nombre completo del primer tipo del archivo de origen. Por ejemplo, si *Type.cs* está en la misma ubicación que *Type.resx*, el nombre generado del manifiesto es *Namespace.Classname.resources*. Con todo, si modifica cualquiera de los atributos de la propiedad `EmbeddedResource` del archivo *.resx*, el nombre de archivo de manifiesto generado puede ser diferente:

- Si se establece el atributo `LogicalName` en la propiedad `EmbeddedResource`, ese valor se usa como nombre de archivo de manifiesto del recurso.

  Ejemplos:

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **Nombre de archivo de manifiesto del recurso generado**: *SomeName.resources* (independientemente del nombre del archivo *.resx*, de la referencia cultural o de cualquier otro metadato).

- Si no se establece `LogicalName`, pero el atributo `ManifestResourceName` se establece en la propiedad `EmbeddedResource`, se usa su valor, combinado con la extensión de archivo *.resources*, como nombre de archivo de manifiesto del recurso.

  Ejemplos:

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **Nombre de archivo de manifiesto del recurso generado**: *SomeName.resources* o *SomeName.fr-FR.resources*.

- Si no se aplican las reglas anteriores y el atributo `DependentUpon` del elemento `EmbeddedResource` se establece en un archivo de origen, el nombre del tipo de la primera clase del archivo de origen se usa en el nombre de archivo de manifiesto del recurso. Más concretamente, el nombre de archivo generado es *Namespace.Classname\[.Culture].resources*.

  Ejemplos:

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **Nombre de archivo de manifiesto del recurso generado**: *Namespace.Classname.resources* o *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es el nombre de la primera clase de *MyTypes.cs*).

- Si no se aplican las reglas anteriores, `EmbeddedResourceUseDependentUponConvention` es `true` (el valor predeterminado de .NET Core) y hay un archivo de origen en la misma ubicación que un archivo *.resx* que tiene el mismo nombre de archivo base, el archivo *.resx* se hace dependiente del archivo de origen correspondiente y el nombre generado es el mismo que en la regla anterior. Esta es la regla de "configuración predeterminada" de los proyectos de .NET Core.
  
  Ejemplos:
  
  Los archivos *MyTypes.cs* y *MyTypes.resx* o *MyTypes.fr-FR.resx* existen en la misma carpeta.
  
  **Nombre de archivo de manifiesto del recurso generado**: *Namespace.Classname.resources* o *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es el nombre de la primera clase de *MyTypes.cs*).

- Si no se aplica ninguna de las reglas anteriores, el nombre de archivo de manifiesto del recurso generado es *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. La ruta de acceso relativa es el valor del atributo `Link` del elemento `EmbeddedResource` si se ha establecido. En caso contrario, la ruta de acceso relativa es el valor del atributo `Identity` del elemento `EmbeddedResource`. En Visual Studio, esta es la ruta de acceso de la raíz del proyecto al archivo en el Explorador de soluciones.

#### <a name="recommended-action"></a>Acción recomendada

Si no le satisfacen los nombres de manifiesto generados, puede:

- Modificar los metadatos del archivo de recursos según una de las reglas de nomenclatura descritas anteriormente.

- Establecer `EmbeddedResourceUseDependentUponConvention` en `false` en el archivo del proyecto para rechazar la nueva convención por completo:

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > Si los atributos `LogicalName` o `ManifestResourceName` están presentes, se seguirán usando sus valores en el nombre del archivo generado.

#### <a name="category"></a>Categoría

MSBuild

#### <a name="affected-apis"></a>API afectadas

N/D
