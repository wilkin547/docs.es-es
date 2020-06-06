---
title: Elemento <assemblyBinding> para <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155484"
---
# <a name="assemblybinding-element-for-configuration"></a>Elemento \<assemblyBinding> para \<configuration>

Especifica la directiva de enlace del ensamblado en el nivel de configuración.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Sintaxis

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **xmlns** | Atributo necesario.<br><br>Especifica el espacio de nombres XML necesario para el enlace de ensamblados. Utilice la cadena "urn: schemas-microsoft-v1" como valor. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-element"></a>Elemento secundario

|     | Descripción |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | Especifica un archivo de configuración para incluirlo. |

## <a name="remarks"></a>Comentarios

El [**\<linkedConfiguration>**](linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar las opciones de configuración del ensamblado.

> [!NOTE]
> El **\<linkedConfiguration>** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Consulte también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
