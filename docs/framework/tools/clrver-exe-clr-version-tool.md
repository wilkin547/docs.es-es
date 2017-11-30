---
title: "Clrver.exe (herramienta de versión de CLR)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 037570e34ec8fd7959fa2a9fd8e22b61aa6db738
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="e4359-102">Clrver.exe (herramienta de versión de CLR)</span><span class="sxs-lookup"><span data-stu-id="e4359-102">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="e4359-103">La herramienta de versión de CLR (Clrver.exe) notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e4359-103">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="e4359-104">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4359-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="e4359-105">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="e4359-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="e4359-106">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e4359-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="e4359-107">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4359-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4359-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4359-108">Syntax</span></span>  
  
```  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="e4359-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="e4359-109">Options</span></span>  
  
|<span data-ttu-id="e4359-110">Opción</span><span class="sxs-lookup"><span data-stu-id="e4359-110">Option</span></span>|<span data-ttu-id="e4359-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4359-111">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="e4359-112">Muestra todos los procesos del equipo que usan CLR.</span><span class="sxs-lookup"><span data-stu-id="e4359-112">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="e4359-113">*pid*</span><span class="sxs-lookup"><span data-stu-id="e4359-113">*pid*</span></span>|<span data-ttu-id="e4359-114">Muestra las versiones de CLR que utiliza el proceso con el identificador de proceso especificado (PID).</span><span class="sxs-lookup"><span data-stu-id="e4359-114">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="e4359-115">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="e4359-115">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4359-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4359-116">Remarks</span></span>  
 <span data-ttu-id="e4359-117">Si llama a Clrver.exe sin opciones, este muestra todas las versiones instaladas de CLR.</span><span class="sxs-lookup"><span data-stu-id="e4359-117">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="e4359-118">Si se especifica un PID para otro usuario, debe tener permisos administrativos para obtener la información de versión.</span><span class="sxs-lookup"><span data-stu-id="e4359-118">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4359-119">En Windows Vista y versiones posteriores, el Control de cuentas de usuario (UAC) determina los privilegios de un usuario.</span><span class="sxs-lookup"><span data-stu-id="e4359-119">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="e4359-120">Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos (tokens) de acceso en tiempo de ejecución: un símbolo (token) de acceso de usuario estándar y un símbolo (token) de acceso de administrador.</span><span class="sxs-lookup"><span data-stu-id="e4359-120">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="e4359-121">De forma predeterminada, se le asignará el rol de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="e4359-121">By default, you are in the standard user role.</span></span> <span data-ttu-id="e4359-122">Para ejecutar código que requiere permisos administrativos, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador.</span><span class="sxs-lookup"><span data-stu-id="e4359-122">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="e4359-123">Para ello, inicie el símbolo del sistema haciendo clic con el botón secundario en el icono de dicho símbolo e indicando que desea ejecutarlo como administrador.</span><span class="sxs-lookup"><span data-stu-id="e4359-123">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="e4359-124">Al intentar determinar la versión de CLR para los procesos SYSTEM, LOCAL SERVICE y NETWORK SERVICE aparece un mensaje que indica que el PID no existe.</span><span class="sxs-lookup"><span data-stu-id="e4359-124">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e4359-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e4359-125">Examples</span></span>  
 <span data-ttu-id="e4359-126">El comando siguiente muestra todas las versiones de CLR instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e4359-126">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="e4359-127">El comando siguiente muestra la versión de CLR que usa el proceso 128.</span><span class="sxs-lookup"><span data-stu-id="e4359-127">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="e4359-128">El comando siguiente muestra todos los procesos administrados y la versión de CLR que usan.</span><span class="sxs-lookup"><span data-stu-id="e4359-128">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="e4359-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4359-129">See Also</span></span>  
 [<span data-ttu-id="e4359-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="e4359-130">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="e4359-131">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="e4359-131">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
