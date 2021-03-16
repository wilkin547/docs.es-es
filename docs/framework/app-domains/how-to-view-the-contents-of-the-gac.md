---
title: Procedimiento para consultar el contenido de la caché global de ensamblados
description: Obtenga información sobre cómo visualizar el contenido de la caché global de ensamblados en .NET mediante el uso de la herramienta de caché global de ensamblados (gacutil.exe).
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: a40c371e6f95f6c90ecbfbf28183226632a58e5b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258317"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Procedimiento para consultar el contenido de la caché global de ensamblados

Use la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.

## <a name="view-the-assemblies-in-the-gac"></a>Ver los ensamblados en la caché global de ensamblados

Para ver una lista de los ensamblados en la caché global de ensamblados, abra un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell) y, a continuación, escriba el siguiente comando:

```shell
gacutil -l
```

o bien

```shell
gacutil /l
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos. A partir de .NET Framework 4, Shfusion.dll está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
