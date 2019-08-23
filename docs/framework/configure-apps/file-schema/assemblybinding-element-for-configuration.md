---
title: Elemento <assemblyBinding> para <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921272"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding > elemento para \<Configuration >

Especifica la directiva de enlace del ensamblado en el nivel de configuración.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<assemblyBinding>**

## <a name="syntax"></a>Sintaxis

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Atributo

|           | DESCRIPCIÓN |
| --------- | ----------- |
| **xmlns** | Atributo necesario.<br><br>Especifica el espacio de nombres XML necesario para el enlace de ensamblados. Utilice la cadena "urn: schemas-microsoft-v1" como valor. |

## <a name="parent-element"></a>Elemento primario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework. |

## <a name="child-element"></a>Elemento secundario

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<linkedConfiguration>** ](linkedconfiguration-element.md) | Especifica un archivo de configuración para incluirlo. |

## <a name="remarks"></a>Comentarios

El elemento > linkedConfiguration simplifica la administración de ensamblados de componentes al permitir que los archivos de configuración de la aplicación incluyan archivos de configuración de ensamblados en ubicaciones conocidas, en lugar de duplicar el ensamblado. [ **\<** ](linkedconfiguration-element.md) Opciones de configuración.

> [!NOTE]
> El elemento > linkedConfiguration no se admite para las aplicaciones con manifiestos en paralelo de Windows.  **\<**

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo incluir un archivo de configuración en el disco duro local:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
