---
title: Filtrar Instalar un ensamblado en la caché global de ensamblados
ms.date: 02/05/2019
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
ms.openlocfilehash: 233a7803cb59f9bfeac15d293dc3fb5a0db449c9
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903760"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Filtrar Instalar un ensamblado en la caché global de ensamblados

La caché global de ensamblados (GAC) almacena los ensamblados que comparten varias aplicaciones. Puede instalar un ensamblado en la [caché global de ensamblados](gac.md) con uno de los componentes siguientes: 
- [Windows Installer](#windows-installer)
- [Herramienta Caché global de ensamblados](#global-assembly-cache-tool)

> [!IMPORTANT]
> En la memoria caché global de ensamblados solamente se pueden instalar ensamblados con nombre seguro. Para obtener información sobre cómo crear un ensamblado de este tipo, vea [Procedimientos para Firmar un ensamblado con un nombre seguro](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), el motor de instalación de Windows, es la manera recomendada para agregar ensamblados a la caché global de ensamblados. Windows Installer proporciona el recuento de referencias de los ensamblados de la caché global de ensamblados, además de otras ventajas. Para crear un paquete de instalación para Windows Installer, use la [extensión del conjunto de herramientas de WiX para Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Herramienta de caché global de ensamblados

Puede usar la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar ensamblados a la caché global de ensamblados y ver el contenido de esa caché.

   > [!NOTE]
   > *Gacutil.exe* solo está pensada para fines de desarrollo. No se usa para instalar ensamblados de producción en la caché global de ensamblados.

La sintaxis para usar *gacutil.exe* para instalar un ensamblado en la GAC es la siguiente:

```console
gacutil -i <assembly name>
```

En este comando, *\<nombre del ensamblado>* es el nombre del ensamblado que se va a instalar en la caché global de ensamblados.

Si *gacutil.exe* no se encuentra en la ruta del sistema, use [Símbolo del sistema para desarrolladores para VS *\<versión >*](../tools/developer-command-prompt-for-vs.md).

En el ejemplo siguiente se instala un ensamblado con el nombre de archivo *hello.dll* en la caché global de ensamblados.

```console
gacutil -i hello.dll
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión *Shfusion.dll* del shell de Windows permitía instalar ensamblados si los arrastraba al Explorador de archivos. A partir de .NET Framework 4, *Shfusion.dll* está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Cómo: Quitar un ensamblado de la memoria caché global de ensamblados](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Herramienta de la caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
- [Cómo: Firmar un ensamblado con un nombre seguro](how-to-sign-an-assembly-with-a-strong-name.md)
