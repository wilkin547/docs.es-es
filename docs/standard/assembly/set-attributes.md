---
title: Establecimiento de atributos de ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0e4e2e595ed4f95511bd23ab0ed00139f71b2c8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740473"
---
# <a name="set-assembly-attributes"></a>Establecimiento de atributos de ensamblado

Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado. Los atributos se dividen en los siguientes conjuntos de información:

- Atributos de identidad del ensamblado

- Atributos informativos

- Atributos de manifiesto del ensamblado

- Atributos de nombre seguro

## <a name="assembly-identity-attributes"></a>Atributos de identidad del ensamblado

Tres atributos, junto con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural. Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia el ensamblado en el código. Puede usar atributos para establecer la versión y la referencia cultural de un ensamblado. El compilador o el [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) establecen el valor de nombre cuando se crea el ensamblado, basándose en el archivo que contiene el manifiesto del ensamblado.

En la tabla siguiente se describen los atributos de versión y de referencia cultural.

|Atributo de identidad del ensamblado|Description|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|Campo enumerado que indica la referencia cultural que admite el ensamblado. Un ensamblado también puede especificar independencia de la referencia cultural, lo que indica que contiene los recursos para la referencia cultural predeterminada. **Nota:** El tiempo de ejecución trata cualquier ensamblado que no tenga el atributo de referencia cultural establecido en NULL como un ensamblado satélite. Estos ensamblados están sujetos a las reglas de enlace de ensamblados satélite. Para más información, consulte [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md).|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Valor que establece atributos de ensamblado, como por ejemplo, si se puede ejecutar el ensamblado en paralelo.|
|<xref:System.Reflection.AssemblyVersionAttribute>|Valor numérico con el formato *versión_principal*.*versión_secundaria*.*compilación*.*revisión* (por ejemplo, 2.4.0.0). Common Language Runtime usa este valor para realizar operaciones de enlace en ensamblados con nombre seguro. **Nota:** Si el atributo <xref:System.Reflection.AssemblyInformationalVersionAttribute> no se aplica a un ensamblado, el número de versión que especifica el atributo <xref:System.Reflection.AssemblyVersionAttribute> lo usan las propiedades <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.|

En el ejemplo de código siguiente se muestra cómo aplicar los atributos de versión y referencia cultural a un ensamblado.

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a>Atributos informativos

Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado. En la tabla siguiente se describen los atributos informativos que se pueden aplicar a un ensamblado.

|Atributo informativo|Description|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Valor de cadena que especifica un nombre de compañía.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Valor de cadena que especifica información de copyright.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Valor de cadena que especifica el número de versión del archivo Win32. Normalmente el valor predeterminado es la versión del ensamblado.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Valor de cadena que especifica la información de versión que Common Language Runtime no usa, como por ejemplo un número de versión del producto completo. **Nota:** Si este atributo se aplica a un ensamblado, se puede obtener la cadena que especifica en tiempo de ejecución mediante la propiedad <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>. La cadena también se utiliza en la clave del Registro y la ruta de acceso que proporcionan las propiedades <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> .|
|<xref:System.Reflection.AssemblyProductAttribute>|Valor de cadena que especifica la información del producto.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Valor de cadena que especifica la información de marca comercial.|

Estos atributos pueden aparecer en la página Propiedades de Windows del ensamblado o se pueden reemplazar con la opción del compilador **/win32res** para especificar su propio archivo de recursos de Win32.

## <a name="assembly-manifest-attributes"></a>Atributos de manifiesto del ensamblado

Puede utilizar atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado, incluidos el título, la descripción, el alias predeterminado y la configuración. En la tabla siguiente se describen los atributos de manifiesto del ensamblado.

|Atributo de manifiesto del ensamblado|Description|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Valor de cadena que indica la configuración del ensamblado, como Retail o Debug. El tiempo de ejecución no utiliza este valor.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Valor de cadena que especifica un alias predeterminado que utilizarán los ensamblados de referencia. Este valor proporciona un nombre descriptivo cuando el nombre del ensamblado no es descriptivo por sí solo (por ejemplo, un valor GUID). Este valor también puede utilizarse como una forma abreviada del nombre completo del ensamblado.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Valor de cadena que especifica una breve descripción que resume la naturaleza y el propósito del ensamblado.|
|<xref:System.Reflection.AssemblyTitleAttribute>|Valor de cadena que especifica un nombre descriptivo para el ensamblado. Por ejemplo, un ensamblado denominado *comdlg* puede tener el título “Microsoft Common Dialog Control”.|

## <a name="strong-name-attributes"></a>Atributos de nombre seguro

Puede utilizar atributos de nombre seguro para establecer un nombre seguro para un ensamblado. En la tabla siguiente se describen los atributos de nombre seguro.

|Atributos de nombre seguro|Description|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|Valor booleano que indica que se está usando la firma retardada.|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|Valor de cadena que indica el nombre del archivo que contiene la clave pública (si se usa la firma retardada) o las claves públicas y privadas que se pasan como un parámetro al constructor de este atributo. Tenga en cuenta que el nombre de archivo es relativo a la ruta de acceso del archivo de salida ( *.exe* o *.dll*), no a la ruta de acceso del archivo de origen.|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|Indica el contenedor de claves que contiene el par de claves que se pasa como parámetro al constructor de este atributo.|

En el ejemplo de código siguiente, se muestran los atributos que se aplicarán cuando se use la firma retardada para crear un ensamblado con nombre seguro con un archivo de clave pública denominado *myKey.snk*.

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a>Vea también

- [Creación de ensamblados](create.md)
