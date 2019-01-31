---
title: Procedimiento para determinar las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas
description: Aprenda a determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e11b2588471e95b4e47fd0efaf41757430b9bb39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604191"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Procedimiento para determinar las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas

En este artículo se muestra cómo determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.

> [!NOTE]
> Todas las técnicas que se muestran en este artículo requieren una cuenta con privilegios administrativos.

## <a name="to-find-installed-updates-using-the-registry"></a>Búsqueda de las actualizaciones instaladas mediante el Registro

Las actualizaciones de seguridad y las revisiones instaladas para cada versión de .NET Framework instalada en un equipo se enumeran en el Registro de Windows. Puede utilizar el Editor del Registro (*regedit.exe*) para ver esta información.

1. Abra el programa **regedit.exe**. En Windows 8 y versiones posteriores, haga clic en **Inicio** ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") y, a continuación, seleccione **Ejecutar**. En el cuadro **Abrir**, escriba **regedit.exe** y seleccione **Aceptar**.

2. En el Editor del Registro, abra la subclave siguiente:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican. Cada actualización se identifica mediante un número de la Knowledge Base (KB).

En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves. Para obtener información sobre cómo detectar los números de versión instalados, vea [Procedimiento para determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Búsqueda de las actualizaciones instaladas mediante la consulta al Registro en código

El ejemplo siguiente determina mediante programación las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

El ejemplo genera un resultado similar al siguiente:

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Búsqueda de las actualizaciones instaladas mediante la consulta al Registro en PowerShell

El ejemplo siguiente muestra cómo determinar las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo mediante PowerShell:

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

El ejemplo genera un resultado similar al siguiente:

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

## <a name="see-also"></a>Vea también

- [Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)
- [Instalación de .NET Framework para desarrolladores](../../../docs/framework/install/guide-for-developers.md)
- [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)
