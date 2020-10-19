---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955567"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a>Cambios de comportamiento de API relacionados con ensamblados para el formato de publicación de un solo archivo

Varias API relacionadas con la ubicación de archivos de un ensamblado tienen cambios de comportamiento cuando se invocan en un formato de publicación de un solo archivo.

#### <a name="change-description"></a>Descripción del cambio

En la publicación de un solo archivo para .NET 5.0 y versiones posteriores, los ensamblados empaquetados se cargan desde la memoria en lugar de extraerse en el disco. En el caso de las aplicaciones publicadas de un solo archivo, esto significa que ciertas API relacionadas con la ubicación devuelven valores diferentes en .NET 5.0 y versiones posteriores que en versiones anteriores de .NET. Los cambios son los siguientes:

| API | Versiones anteriores | .NET 5.0 y versiones posteriores |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | Devuelve la ruta de acceso del archivo DLL extraído | Devuelve una cadena vacía para los ensamblados agrupados |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | Devuelve la ruta de acceso del archivo DLL extraído | Inicia una excepción para los ensamblados agrupados |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | Devuelve `null` para los ensamblados agrupados | Inicia una excepción para los ensamblados agrupados |
| `Environment.GetCommandLineArgs()[0]` | El valor es el nombre del punto de entrada del archivo DLL | El valor es el nombre del archivo ejecutable del host |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | El valor es el directorio de extracción temporal | El valor es el directorio contenedor del archivo ejecutable del host |

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="recommended-action"></a>Acción recomendada

Evite las dependencias de la ubicación de archivo de los ensamblados al publicarlos como un solo archivo.

#### <a name="category"></a>Categoría

- Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
