---
title: Procedimiento para consultar el contenido de la caché global de ensamblados
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c7d197ea7178abf991247e5ecca02c2b8e94713
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634371"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Procedimiento para consultar el contenido de la caché global de ensamblados

Use la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.

## <a name="view-the-assemblies-in-the-gac"></a>Ver los ensamblados en la caché global de ensamblados

Para ver una lista de los ensamblados en la caché global de ensamblados, abra el [Símbolo del sistema para desarrolladores de Visual Studio](../tools/developer-command-prompt-for-vs.md) y, a continuación, escriba el siguiente comando:

```shell
gacutil -l
```

o bien

```shell
gacutil /l
```

> [!NOTE]
> En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos. A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.

## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
