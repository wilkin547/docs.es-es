---
title: Clrver.exe (herramienta de versión de CLR)
description: Revise Clrver.exe, la herramienta de versión de CLR. Esta herramienta notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: 8205b92f3997f6abacc566e2e6f2b37604fbda07
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255254"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="f49b4-104">Clrver.exe (herramienta de versión de CLR)</span><span class="sxs-lookup"><span data-stu-id="f49b4-104">Clrver.exe (CLR Version Tool)</span></span>

<span data-ttu-id="f49b4-105">La herramienta de versión de CLR (Clrver.exe) notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f49b4-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="f49b4-106">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f49b4-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f49b4-107">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="f49b4-107">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="f49b4-108">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f49b4-108">At the command prompt, enter the following command:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49b4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f49b4-109">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="f49b4-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="f49b4-110">Options</span></span>  
  
|<span data-ttu-id="f49b4-111">Opción</span><span class="sxs-lookup"><span data-stu-id="f49b4-111">Option</span></span>|<span data-ttu-id="f49b4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f49b4-112">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="f49b4-113">Muestra todos los procesos del equipo que usan CLR.</span><span class="sxs-lookup"><span data-stu-id="f49b4-113">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="f49b4-114">*pid*</span><span class="sxs-lookup"><span data-stu-id="f49b4-114">*pid*</span></span>|<span data-ttu-id="f49b4-115">Muestra las versiones de CLR que utiliza el proceso con el identificador de proceso especificado (PID).</span><span class="sxs-lookup"><span data-stu-id="f49b4-115">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="f49b4-116">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="f49b4-116">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f49b4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f49b4-117">Remarks</span></span>  

 <span data-ttu-id="f49b4-118">Si llama a Clrver.exe sin opciones, este muestra todas las versiones instaladas de CLR.</span><span class="sxs-lookup"><span data-stu-id="f49b4-118">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="f49b4-119">Si se especifica un PID para otro usuario, debe tener permisos administrativos para obtener la información de versión.</span><span class="sxs-lookup"><span data-stu-id="f49b4-119">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f49b4-120">En Windows Vista y versiones posteriores, el Control de cuentas de usuario (UAC) determina los privilegios de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f49b4-120">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="f49b4-121">Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos (tokens) de acceso en tiempo de ejecución: un símbolo (token) de acceso de usuario estándar y un símbolo (token) de acceso de administrador.</span><span class="sxs-lookup"><span data-stu-id="f49b4-121">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="f49b4-122">De forma predeterminada, se le asignará el rol de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="f49b4-122">By default, you are in the standard user role.</span></span> <span data-ttu-id="f49b4-123">Para ejecutar código que requiere permisos administrativos, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador.</span><span class="sxs-lookup"><span data-stu-id="f49b4-123">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="f49b4-124">Para ello, inicie el símbolo del sistema haciendo clic con el botón secundario en el icono de dicho símbolo e indicando que desea ejecutarlo como administrador.</span><span class="sxs-lookup"><span data-stu-id="f49b4-124">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="f49b4-125">Al intentar determinar la versión de CLR para los procesos SYSTEM, LOCAL SERVICE y NETWORK SERVICE aparece un mensaje que indica que el PID no existe.</span><span class="sxs-lookup"><span data-stu-id="f49b4-125">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f49b4-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f49b4-126">Examples</span></span>  

 <span data-ttu-id="f49b4-127">El comando siguiente muestra todas las versiones de CLR instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f49b4-127">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="f49b4-128">El comando siguiente muestra la versión de CLR que usa el proceso 128.</span><span class="sxs-lookup"><span data-stu-id="f49b4-128">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="f49b4-129">El comando siguiente muestra todos los procesos administrados y la versión de CLR que usan.</span><span class="sxs-lookup"><span data-stu-id="f49b4-129">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="f49b4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49b4-130">See also</span></span>

- [<span data-ttu-id="f49b4-131">Herramientas</span><span class="sxs-lookup"><span data-stu-id="f49b4-131">Tools</span></span>](index.md)
- [<span data-ttu-id="f49b4-132">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="f49b4-132">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
