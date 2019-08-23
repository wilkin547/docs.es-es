---
title: Elemento <linkedConfiguration>
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
ms.openlocfilehash: a0b56ac66302f11c59c149197a84bb96691282a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921012"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration >, elemento

Especifica un archivo de configuración para incluirlo.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration>**

## <a name="syntax"></a>Sintaxis

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Atributo

|           | DESCRIPCIÓN |
| --------- | ----------- |
| **href**  | Atributo necesario.<br><br>Dirección URL del archivo de configuración que se va a incluir. El único formato admitido para el atributo href `file://`es. Se admiten los archivos locales y los archivos UNC. |

## <a name="parent-element"></a>Elemento primario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [assemblyBinding >, elemento  **\<** ](assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración. |

## <a name="child-elements"></a>Elementos secundarios

None

## <a name="remarks"></a>Comentarios

El elemento  **\<> linkedConfiguration** simplifica el servicio de los ensamblados de componentes. Si una o más aplicaciones usan un ensamblado que tiene un archivo de configuración que reside en una ubicación conocida, los archivos de configuración de las aplicaciones que usan el ensamblado pueden  **\<** usar el elemento > de linkedConfiguration para incluir el archivo de configuración del ensamblado, en lugar de incluir la información de configuración directamente. Cuando se da servicio al ensamblado del componente, al actualizar el archivo de configuración común se proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.

> [!NOTE]
> El elemento > linkedConfiguration no se admite para las aplicaciones con manifiestos en paralelo de Windows.  **\<**

Las siguientes reglas rigen el uso de archivos de configuración vinculados:

- Los valores de los archivos de configuración incluidos solo afectan a la Directiva de enlace del cargador y solo los usa el cargador. Los archivos de configuración incluidos pueden tener valores distintos de las directivas de enlace, pero esa configuración no tiene ningún efecto.

- El único formato admitido para `href` el atributo `file://`es. Se admiten los archivos locales y los archivos UNC.

- No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.

- Todos los archivos de configuración vinculados se combinan para formar un archivo, de forma similar al `#include` comportamiento de la directivaC++en C/.

- **El\<elemento > de linkedConfiguration** solo se permite en los archivos de configuración de la aplicación; se omite en el *archivo Machine. config*.

- Las referencias circulares se detectan y finalizan. Es decir, si  **\<linkedConfiguration >** elementos de una serie de archivos de configuración forman un bucle, el bucle se detecta y se detiene.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo incluir el archivo de configuración desde el disco duro local:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vea también

- [assemblyBinding >, elemento  **\<** ](assemblybinding-element-for-configuration.md)
- [Esquema del archivo de configuración para el .NET Framework](index.md)
