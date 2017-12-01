---
title: "Cómo: determinar qué revisiones y actualizaciones de seguridad de .NET Framework están instaladas"
description: "Obtenga información acerca de cómo determinar qué actualizaciones de seguridad de .NET Framework y las revisiones se instalan en un equipo."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Cómo: determinar qué revisiones y actualizaciones de seguridad de .NET Framework están instaladas

Este artículo muestra cómo averiguar qué seguridad de .NET Framework de actualizaciones y revisiones se instalan en un equipo.

> [!NOTE]
> Todas las técnicas que se muestra en este artículo requieren una cuenta con privilegios administrativos.

## <a name="to-find-installed-updates-using-the-registry"></a>Para buscar las actualizaciones instaladas mediante el registro

Las actualizaciones de seguridad instaladas y revisiones para cada versión de .NET Framework instalada en un equipo se muestran en el registro de Windows. Puede usar el Editor del registro (*regedit.exe*) programa para ver esta información.

1. Abra el programa **regedit.exe**. En Windows 8 y versiones posteriores, haga clic en **iniciar** ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), a continuación, seleccione **ejecutar**. En el **abiertos** cuadro, escriba **regedit** y seleccione **Aceptar**.

2. En el Editor del Registro, abra la subclave siguiente:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican. Cada actualización se identifica mediante un número de la Knowledge Base (KB).

En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves. Para obtener información sobre cómo detectar los números de versión instalada, consulte [Cómo: determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Para buscar actualizaciones instaladas consultando el registro en el código

En el ejemplo siguiente se determina mediante programación las actualizaciones de seguridad de .NET Framework y revisiones que se instalan en un equipo:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

El ejemplo genera una salida similar a la siguiente:

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Para buscar actualizaciones instaladas consultando el registro en PowerShell

En el ejemplo siguiente se muestra cómo determinar las actualizaciones de seguridad de .NET Framework y revisiones que se instalan en un equipo con PowerShell:

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

El ejemplo genera una salida similar a la siguiente:

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>Vea también

[Cómo: determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Instalar .NET Framework para desarrolladores](../../../docs/framework/install/guide-for-developers.md)  
[Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)
