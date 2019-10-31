---
title: Instalación de un ensamblado en la caché global de ensamblados
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: e670f5dba47393b7df047fb4e6f7d92df8cb187c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119802"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Instalación de un ensamblado en la caché global de ensamblados

La caché global de ensamblados (GAC) almacena los ensamblados que comparten varias aplicaciones. Puede instalar un ensamblado en la [caché global de ensamblados](gac.md) con uno de los componentes siguientes: 

- [Windows Installer](#windows-installer)
- [Herramienta de la caché global de ensamblados](#global-assembly-cache-tool)

> [!IMPORTANT]
> Solamente puede instalar ensamblados con nombre seguro en la caché global de ensamblados. Para obtener información sobre cómo crear un ensamblado con nombre seguro, vea [Cómo: firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados. Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas. Para crear un paquete de instalación para Windows Installer, use la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Caché global de ensamblados (herramienta)

Puede usar la [utilidad de la caché global de ensamblados (gacutil.exe) de .NET](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados a la caché global de ensamblados y ver el contenido de esa caché.

   > [!NOTE]
   > *Gacutil.exe* solo está pensada para fines de desarrollo. No se usa para instalar ensamblados de producción en la caché global de ensamblados.

La sintaxis para usar *gacutil.exe* para instalar un ensamblado en la GAC es la siguiente:

```cmd
gacutil -i <assembly name>
```

En este comando, *\<nombre del ensamblado>* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.

Si *gacutil.exe* no se encuentra en la ruta de acceso del sistema, use [Símbolo del sistema para desarrolladores de Visual Studio *\<versión>* ](../tools/developer-command-prompt-for-vs.md).

En el ejemplo siguiente se instala un ensamblado con el nombre de archivo *hello.dll* en la caché global de ensamblados.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión *Shfusion.dll* del shell de Windows permitía instalar ensamblados si los arrastraba al Explorador de archivos. A partir de .NET Framework 4, *Shfusion.dll* está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Cómo: quitar un ensamblado de la caché global de ensamblados](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (herramienta de la caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
- [Cómo: firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md)
