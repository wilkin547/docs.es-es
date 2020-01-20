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
ms.openlocfilehash: 087519048b412798ef7495d250dc2538ee5c2fd0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716252"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="3cc4c-103">Determinación de las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas</span><span class="sxs-lookup"><span data-stu-id="3cc4c-103">How to determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="3cc4c-104">En este artículo se muestra cómo determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="3cc4c-105">Todas las técnicas que se muestran en este artículo requieren una cuenta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="use-registry-editor"></a><span data-ttu-id="3cc4c-106">Uso del Editor del Registro</span><span class="sxs-lookup"><span data-stu-id="3cc4c-106">Use Registry Editor</span></span>

<span data-ttu-id="3cc4c-107">Las actualizaciones de seguridad y las revisiones instaladas para cada versión de .NET Framework instalada en un equipo se enumeran en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="3cc4c-108">Puede utilizar el Editor del Registro (*regedit.exe*) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="3cc4c-109">Abra el programa **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="3cc4c-110">En Windows 8 y versiones posteriores, haga clic con el botón derecho en **Inicio** ![Captura de pantalla de la tecla del logotipo de Windows](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo") y seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="3cc4c-111">En el cuadro **Abrir**, escriba **regedit.exe** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="3cc4c-112">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cc4c-112">In the Registry Editor, open the following subkey:</span></span>

     <span data-ttu-id="3cc4c-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span><span class="sxs-lookup"><span data-stu-id="3cc4c-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span></span>

     <span data-ttu-id="3cc4c-114">Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-114">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="3cc4c-115">Cada actualización se identifica mediante un número de la Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="3cc4c-115">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="3cc4c-116">En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves.</span><span class="sxs-lookup"><span data-stu-id="3cc4c-116">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="3cc4c-117">Para obtener información sobre cómo detectar los números de versión instalados, vea [Procedimiento para determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="3cc4c-117">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="query-the-registry-using-code"></a><span data-ttu-id="3cc4c-118">Consulta del registro mediante código</span><span class="sxs-lookup"><span data-stu-id="3cc4c-118">Query the registry using code</span></span>

<span data-ttu-id="3cc4c-119">El ejemplo siguiente determina mediante programación las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo:</span><span class="sxs-lookup"><span data-stu-id="3cc4c-119">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="3cc4c-120">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cc4c-120">The example produces an output that's similar to the following one:</span></span>

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

## <a name="use-powershell-to-query-the-registry"></a><span data-ttu-id="3cc4c-121">Uso de PowerShell para consultar el registro</span><span class="sxs-lookup"><span data-stu-id="3cc4c-121">Use PowerShell to query the registry</span></span>

<span data-ttu-id="3cc4c-122">El ejemplo siguiente muestra cómo determinar las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo mediante PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3cc4c-122">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="3cc4c-123">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3cc4c-123">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3cc4c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cc4c-124">See also</span></span>

- [<span data-ttu-id="3cc4c-125">Cómo: Determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="3cc4c-125">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="3cc4c-126">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="3cc4c-126">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="3cc4c-127">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="3cc4c-127">Versions and dependencies</span></span>](versions-and-dependencies.md)
