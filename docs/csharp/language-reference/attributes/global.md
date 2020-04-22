---
title: 'Atributos reservados de C#: Atributos globales'
ms.date: 04/09/2020
description: Los atributos proporcionan metadatos que el compilador usa para comprender más semántica del programa
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389809"
---
# <a name="reserved-attributes-assembly-level-attributes"></a>Atributos reservados: atributos de nivel de ensamblado

La mayoría de los atributos se aplican a elementos específicos del lenguaje, como las clases o los métodos, aunque algunos atributos son globales (se aplican a todo un ensamblado o módulo). Por ejemplo, el atributo <xref:System.Reflection.AssemblyVersionAttribute> se puede usar para insertar información de versión en un ensamblado, como en este ejemplo:

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

Los atributos globales aparecen en el código fuente después de cualquier directiva `using` de nivel superior y antes de cualquier declaración de tipo, módulo o espacio de nombres. Los atributos globales pueden aparecer en varios archivos de código fuente, pero estos archivos se deben compilar en un solo paso de compilación. Visual Studio agrega atributos globales al archivo AssemblyInfo.cs en proyectos de .NET Framework. Estos atributos no se agregan a los proyectos de .NET Core.

Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado. Se dividen en las siguientes categorías:

- Atributos de identidad del ensamblado
- Atributos informativos
- Atributos de manifiesto del ensamblado

## <a name="assembly-identity-attributes"></a>Atributos de identidad del ensamblado

Tres atributos, con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural. Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia a este en el código. Puede establecer la versión y la referencia cultural de un ensamblado mediante atributos, pero el valor de nombre lo establece el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](/visualstudio/ide/reference/assembly-information-dialog-box) o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado. El nombre del ensamblado se basa en el manifiesto del ensamblado. El atributo <xref:System.Reflection.AssemblyFlagsAttribute> especifica si pueden coexistir varias copias del ensamblado.

En la siguiente tabla se muestran los atributos de identidad.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|Especifica la versión de un ensamblado.|
|<xref:System.Reflection.AssemblyCultureAttribute>|Especifica la cultura que admite el ensamblado.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.|

## <a name="informational-attributes"></a>Atributos informativos

Puede usar atributos informativos para proporcionar información adicional de la empresa o el producto para un ensamblado. En la tabla siguiente se muestran los atributos informativos definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Especifica un nombre de producto para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Especifica una marca comercial para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Especifica una versión informativa para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Especifica un nombre de empresa para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Define un atributo personalizado que especifica un copyright para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Establece un número de versión específico para el recurso de versión de archivo Win32.|
|<xref:System.CLSCompliantAttribute>|Indica si el ensamblado es compatible con Common Language Specification (CLS).|

## <a name="assembly-manifest-attributes"></a>Atributos de manifiesto del ensamblado

Puede usar los atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado Los atributos incluyen el título, la descripción, el alias predeterminado y la configuración. En la tabla siguiente se muestran los atributos de manifiesto del ensamblado definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.

|Atributo|Propósito|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Especifica un título de ensamblado para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Especifica una descripción de ensamblado para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Especifica una configuración de ensamblado (por ejemplo, comercial o depuración) para un manifiesto del ensamblado.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Define un alias descriptivo predeterminado para un manifiesto del ensamblado.|
