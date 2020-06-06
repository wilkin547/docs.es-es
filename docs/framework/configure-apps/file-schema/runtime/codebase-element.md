---
title: <codeBase> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70971884"
---
# <a name="codebase-element"></a>\<codeBase> (Elemento)

Especifica dónde puede encontrar un ensamblado el Common Language Runtime.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a>Sintaxis

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`href`|Atributo necesario.<br /><br /> Especifica la dirección URL en la que el tiempo de ejecución puede encontrar la versión especificada del ensamblado.|
|`version`|Atributo necesario.<br /><br /> Especifica la versión del ensamblado al que se aplica el código base. El formato de un número de versión de ensamblado es *principal. secundaria. compilación. revisión*.|

## <a name="version-attribute"></a>version (atributo)

|Value|Descripción|
|-----------|-----------------|
|Los valores válidos para cada parte del número de versión son de 0 a 65535.|No aplicable.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`buildproviders`|Define una colección de proveedores de generación que se utiliza para compilar archivos de recursos personalizados. Puede tener cualquier número de proveedores de generación.|
|`compilation`|Configura todos los valores de compilación que usa ASP.NET.|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`System.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|

## <a name="remarks"></a>Comentarios

Para que el motor en tiempo de ejecución use la **\<codeBase>** configuración de un archivo de configuración del equipo o un archivo de directiva de edición, el archivo también debe redirigir la versión del ensamblado. Los archivos de configuración de la aplicación pueden tener una configuración de código base sin redirigir la versión del ensamblado. Después de determinar la versión de ensamblado que se va a usar, el tiempo de ejecución aplica la configuración de código base del archivo que determina la versión. Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la manera habitual.

Si el ensamblado tiene un nombre seguro, la configuración de código base puede estar en cualquier parte de la Intranet local o Internet. Si el ensamblado es un ensamblado privado, la configuración de código base debe ser una ruta de acceso relativa al directorio de la aplicación.

En el caso de los ensamblados sin un nombre seguro, se omite la versión y el cargador usa la primera aparición de \<codebase> dentro de \<dependentAssembly> . Si hay una entrada en el archivo de configuración de la aplicación que redirige el enlace a otro ensamblado, la redirección tendrá prioridad aunque la versión del ensamblado no coincida con la solicitud de enlace.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo especificar dónde puede encontrar un ensamblado el tiempo de ejecución.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Consulte también

- [Esquema de configuración en tiempo de ejecución](index.md)
- [Esquema del archivo de configuración](../index.md)
- [Especificar la ubicación de un ensamblado](../../../../standard/assembly/location.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
