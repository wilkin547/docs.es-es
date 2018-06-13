---
title: '&lt;linkedConfiguration&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 71769efa1233fc8a693219dc02ae56ea39c164e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743802"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > elemento

Especifica un archivo de configuración para incluirlo.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**

## <a name="syntax"></a>Sintaxis

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **href**  | Atributo necesario.<br><br>La dirección URL del archivo de configuración para incluir. El único formato compatible para la **href** atributo es `file://`. Se admiten archivos locales y archivos UNC. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<assemblyBinding >** elemento](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración. |

## <a name="child-elements"></a>Elementos secundarios

Ninguna

## <a name="remarks"></a>Comentarios

El  **\<linkedConfiguration >** elemento simplifica el servicio para los ensamblados de componente. Si una o varias aplicaciones utilizan un ensamblado que tiene un archivo de configuración que residen en una ubicación conocida, los archivos de configuración de las aplicaciones que utilizan el ensamblado se pueden usar el  **\<linkedConfiguration >** elemento que se va a incluir el archivo de configuración de ensamblado, en lugar de incluir información de configuración directamente. Cuando se repara el ensamblado de componente, actualizar el archivo de configuración comunes proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.

> [!NOTE]
> El  **\<linkedConfiguration >** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.

Las reglas siguientes rigen el uso de archivos de configuración vinculados:

- Los valores de configuración incluyen archivos solo afecta a la directiva de enlace de cargador y solo son utilizados por el cargador. Los archivos de configuración incluidos pueden tener valores distintos de las directivas de enlace, pero dicha configuración no tiene ningún efecto.

- El único formato compatible para la `href` atributo es `file://`. Se admiten archivos locales y archivos UNC.

- No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.

- Todos los archivos de configuración vinculados se combinan para formar un único archivo, de forma similar al comportamiento de la `#include` directiva en C o C++.

- El  **\<linkedConfiguration >** elemento solo se permite en archivos de configuración de aplicación; se omite en *Machine.config*.

- Las referencias circulares se detectan y se termina. Es decir, si la  **\<linkedConfiguration >** elementos de una serie de archivos de configuración forman un bucle, se detecta y se detuvo el bucle.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo puede incluir el archivo de configuración desde el disco duro local:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vea también

[**\<assemblyBinding >** elemento](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[Esquema de archivos de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
