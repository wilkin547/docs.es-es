---
title: Instalación de un ensamblado en la caché global de ensamblados
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584586"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Instalación de un ensamblado en la caché global de ensamblados

Hay dos formas de instalar un ensamblado con nombre seguro en la caché global de ensamblados.

> [!IMPORTANT]
> En la memoria caché global de ensamblados solamente se pueden instalar ensamblados con nombre seguro. Para obtener información sobre cómo crear un ensamblado con nombre seguro, vea [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md) (Cómo: Firmar un ensamblado con un nombre seguro).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados. Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas. Puede usar la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) para crear un paquete de instalación para Windows Installer.

## <a name="global-assembly-cache-tool"></a>Herramienta de caché global de ensamblados

Puede usar la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados con nombre seguro a la caché global de ensamblados y ver el contenido de dicha caché.

   > [!NOTE]
   > Gacutil.exe sólo debe usarse para programación y no para instalar ensamblados de producción en la caché global de ensamblados.

La sintaxis de gacutil es la siguiente:

```shell
gacutil -i <assembly name>
```

En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.

En el ejemplo siguiente se instala un ensamblado con el nombre de archivo `hello.dll` en la caché global de ensamblados.

```shell
gacutil -i hello.dll
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión Shfusion.dll del shell de Windows le permitía instalar ensamblados arrastrándolos en el **Explorador de archivos**. A partir de .NET Framework 4, Shfusion.dll está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Quitar un ensamblado de la memoria caché global de ensamblados](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
- [Cómo: Firmar un ensamblado con un nombre seguro](how-to-sign-an-assembly-with-a-strong-name.md)