---
title: Procedimiento para quitar un ensamblado de la memoria caché global de ensamblados
description: Aprenda a quitar un ensamblado de la caché global de ensamblados en .NET mediante la herramienta de caché global de ensamblados (Gacutil.exe) o Windows Installer.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
ms.openlocfilehash: e3a596ea6029ded190c33032e96b601de9d4012d
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104772"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a>Procedimiento para quitar un ensamblado de la memoria caché global de ensamblados

Hay dos formas de quitar un ensamblado de la caché global de ensamblados (GAC):

- Con la [herramienta Caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md). Puede usar esta opción para desinstalar los ensamblados que haya colocado en la GAC durante el desarrollo y las pruebas.

- Con [Windows Installer](/windows/desktop/Msi/windows-installer-portal). Debe usar esta opción para desinstalar ensamblados al probar los paquetes de instalación y en sistemas de producción.

## <a name="removing-an-assembly-with-gacutilexe"></a>Quitar un ensamblado con Gacutil.exe

En el símbolo del sistema, escriba el siguiente comando:

**gacutil –u** \<*assembly name*>

En este comando, *nombre del ensamblado* es el nombre del ensamblado que se va a quitar de la caché global de ensamblados.

> [!WARNING]
> No debe utilizar Gacutil.exe para quitar ensamblados en sistemas de producción porque existe la posibilidad de que alguna aplicación necesite aún el ensamblado. En su lugar, debe usar el instalador de Windows, que mantiene un recuento de referencias para cada ensamblado que se instala en la GAC.

En el ejemplo siguiente se quita un ensamblado llamado `hello.dll` de la caché global de ensamblados:

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a>Quitar un ensamblado con Windows Installer

En la aplicación **Programas y características** del **Panel de Control**, seleccione la aplicación que quiere desinstalar. Si el paquete de instalación colocó ensamblados en la GAC, Windows Installer los quitará si otra aplicación no lo está usando.

> [!NOTE]
> Windows Installer mantiene un recuento de referencias para los ensamblados instalados en la GAC. Un ensamblado se quita de la GAC solo cuando su recuento de referencias llega a cero, lo que indica que no lo está usando ninguna aplicación instalada por un paquete de Windows Installer.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Cómo: Instalar un ensamblado en la caché global de ensamblados](install-assembly-into-gac.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
