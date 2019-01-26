---
title: '&lt;assemblyBinding&gt; (elemento) para &lt;configuración&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083904"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding > (elemento) para \<configuración >

Especifica la directiva de enlace del ensamblado en el nivel de configuración.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<assemblyBinding>**

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
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-element"></a>Elemento secundario

|     | Descripción |
| --- | ----------- |
| [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | Especifica un archivo de configuración para incluirlo. |

## <a name="remarks"></a>Comentarios

El [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de aplicación para incluir ensamblado en los archivos de configuración ubicaciones conocidas, en lugar de duplicar valores de configuración del ensamblado.

> [!NOTE]
> El  **\<linkedConfiguration >** elemento no se admite para las aplicaciones con manifiestos en paralelo de Windows.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra cómo incluir un archivo de configuración en el disco duro local:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de archivo de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
