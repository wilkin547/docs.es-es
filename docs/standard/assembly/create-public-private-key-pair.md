---
title: Procedimiento para crear un par de claves privada y pública
description: Aprenda a crear un par de claves criptográficas pública y privada para usarlo durante la compilación para crear un ensamblado con un nombre seguro.
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 675871170e7fd4171f0fe09b04d1dbb8906beda4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378551"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Procedimiento para crear un par de claves privada y pública

Para firmar un ensamblado con un nombre seguro, debe disponer de un par de claves privada/pública. Este par de claves criptográficas pública y privada se utiliza durante la compilación para crear un ensamblado con un nombre seguro. Puede crear un par de claves utilizando la [Herramienta Nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md). Normalmente, los archivos de par de claves tienen la extensión *.snk*.

> [!NOTE]
> En Visual Studio, las páginas de propiedades de proyecto de C# y Visual Basic incluyen una pestaña **Firma** que le permite seleccionar los archivos de clave existentes o generar nuevos archivos de clave sin usar *Sn.exe*. En Visual C++, puede especificar la ubicación de un archivo de clave existente en la página de propiedades **Avanzadas** de la sección **Vinculador** de la sección **Propiedades de configuración** de la ventana **Páginas de propiedades**. El uso del atributo <xref:System.Reflection.AssemblyKeyFileAttribute> para identificar los pares de archivo de clave se ha quedado obsoleto empezando por Visual Studio 2005.

## <a name="create-a-key-pair"></a>Creación de un par de claves

Para crear un par de claves, en un símbolo del sistema, escriba el siguiente comando:

**sn –k** \<*file name*>

En este comando, *nombre de archivo* es el nombre del archivo de salida que contiene el par de claves.

En el siguiente ejemplo se crea un par de claves denominado *sgKey.snk*.

```cmd
sn -k sgKey.snk
```

Si desea retrasar la firma de un ensamblado y controlar el par de claves completo (que es poco probable que esté fuera de los escenarios de prueba), puede usar los siguientes comandos para generar un par de claves y, a continuación, extraer la clave pública a partir de él en un archivo independiente. Primero, cree el par de claves:

```cmd
sn -k keypair.snk
```

A continuación, extraiga la clave pública del par de claves y cópiela en un archivo independiente:

```cmd
sn -p keypair.snk public.snk
```

Una vez creado el par de claves, debe colocar el archivo donde las herramientas de inicio de sesión de nombre seguro puedan encontrarlo.

Al firmar un ensamblado con un nombre seguro, la [herramienta Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) busca el archivo de clave en relación con el directorio actual y el directorio de salida. Si se usan compiladores de la línea de comandos, no hay más que copiar la clave en el directorio actual que contenga los módulos de código.

Si está usando una versión anterior de Visual Studio que no tiene una pestaña **Firma** en las propiedades del proyecto, la ubicación recomendada del archivo de clave es el directorio del proyecto con el atributo de archivo especificado de la siguiente forma:

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a>Vea también

- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)
