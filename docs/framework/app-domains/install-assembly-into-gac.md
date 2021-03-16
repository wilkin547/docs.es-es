---
title: Procedimiento Instalar un ensamblado en la caché global de ensamblados
description: Instale un ensamblado en la caché global de ensamblados (GAC) en .NET de modo que se pueda compartir con muchas aplicaciones. Use Windows Installer o la utilidad GAC.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 581736d27d8b90430838fc78aa192a3efa21cbb5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258304"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Procedimiento Instalar un ensamblado en la caché global de ensamblados

La caché global de ensamblados (GAC) almacena los ensamblados que comparten varias aplicaciones. Puede instalar un ensamblado en la [caché global de ensamblados](gac.md) con uno de los componentes siguientes:

- [Windows Installer](#windows-installer)
- [Herramienta de la caché global de ensamblados](#global-assembly-cache-tool)

> [!IMPORTANT]
> Solamente puede instalar ensamblados con nombre seguro en la caché global de ensamblados. Para obtener información sobre cómo crear un ensamblado de este tipo, vea [Procedimientos para Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados. Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas. Para crear un paquete de instalación para Windows Installer, use la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Herramienta de la caché global de ensamblados

Puede usar la [utilidad de la caché global de ensamblados (gacutil.exe) de .NET](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados a la caché global de ensamblados y ver el contenido de esa caché.

   > [!NOTE]
   > *Gacutil.exe* solo está pensada para fines de desarrollo. No se usa para instalar ensamblados de producción en la caché global de ensamblados.

La sintaxis para usar *gacutil.exe* para instalar un ensamblado en la GAC es la siguiente:

```cmd
gacutil -i <assembly name>
```

En este comando, *\<assembly name>* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.

Si *gacutil.exe* no está en la ruta de acceso del sistema, utilice un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).

En el ejemplo siguiente se instala un ensamblado con el nombre de archivo *hello.dll* en la caché global de ensamblados.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión *Shfusion.dll* del shell de Windows permitía instalar ensamblados si los arrastraba al Explorador de archivos. A partir de .NET Framework 4, *Shfusion.dll* está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Cómo: Quitar un ensamblado de la memoria caché global de ensamblados](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (herramienta de la caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
- [Cómo: Firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md)
