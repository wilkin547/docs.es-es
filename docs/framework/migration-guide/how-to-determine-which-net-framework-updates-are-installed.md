---
title: Consulta de las actualizaciones de seguridad y revisiones de .NET Framework instaladas
description: Aprenda a determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 5c7bf48d5786530a9bcb69fb7cf605ac2c80a4eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181271"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Determinación de las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas

En este artículo se muestra cómo determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.

> [!NOTE]
> Todas las técnicas que se muestran en este artículo requieren una cuenta con privilegios administrativos.

## <a name="use-registry-editor"></a>Uso del Editor del Registro

Las actualizaciones de seguridad y las revisiones instaladas para cada versión de .NET Framework instalada en un equipo se enumeran en el Registro de Windows. Puede utilizar el Editor del Registro (*regedit.exe*) para ver esta información.

1. Abra el programa **regedit.exe**. En Windows 8 y versiones posteriores, haga clic con el botón derecho en **Inicio** ![Captura de pantalla de la tecla del logotipo de Windows](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo") y seleccione **Ejecutar**. En el cuadro **Abrir**, escriba **regedit.exe** y seleccione **Aceptar**.

2. En el Editor del Registro, abra la subclave siguiente:

     **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**

     Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican. Cada actualización se identifica mediante un número de la Knowledge Base (KB).

En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves. Para obtener información sobre cómo detectar los números de la versión instalada, consulte [Cómo: Determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).

## <a name="query-the-registry-using-code"></a>Consulta del registro mediante código

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

## <a name="use-powershell-to-query-the-registry"></a>Uso de PowerShell para consultar el registro

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

- [Cómo: Determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md)
- [Instalación de .NET Framework para desarrolladores](../install/guide-for-developers.md)
- [Versiones y dependencias](versions-and-dependencies.md)
