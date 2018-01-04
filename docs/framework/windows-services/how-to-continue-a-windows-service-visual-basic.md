---
title: "Cómo: Continuar un servicio de Windows (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 73b16a5e5834f7279ae551d4e7efd26cc86c1d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="d32a1-102">Cómo: Continuar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d32a1-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="d32a1-103">Este ejemplo se utiliza la <xref:System.ServiceProcess.ServiceController> componente para reanudar el servicio de administración de IIS en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d32a1-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d32a1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32a1-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="d32a1-105">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d32a1-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="d32a1-106">En el selector de fragmentos de código, se encuentra en **sistema operativo Windows > Servicios de Windows**.</span><span class="sxs-lookup"><span data-stu-id="d32a1-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="d32a1-107">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="d32a1-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d32a1-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d32a1-108">Compiling the Code</span></span>  
 <span data-ttu-id="d32a1-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d32a1-109">This example requires:</span></span>  
  
-   <span data-ttu-id="d32a1-110">Una referencia de proyecto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="d32a1-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="d32a1-111">Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="d32a1-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="d32a1-112">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="d32a1-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="d32a1-113">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d32a1-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d32a1-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d32a1-114">Robust Programming</span></span>  
 <span data-ttu-id="d32a1-115">El <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad de la <xref:System.ServiceProcess.ServiceController> clase es el equipo local de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d32a1-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="d32a1-116">Para hacer referencia a los servicios de Windows en otro equipo, cambie el <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad en el nombre de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="d32a1-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="d32a1-117">No se puede llamar el <xref:System.ServiceProcess.ServiceController.Continue%2A> método en un servicio hasta que el estado del controlador de servicio es <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="d32a1-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="d32a1-118">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="d32a1-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="d32a1-119">No se puede reanudar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d32a1-119">The service cannot be resumed.</span></span> <span data-ttu-id="d32a1-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="d32a1-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="d32a1-121">Error de acceso a la API del sistema.</span><span class="sxs-lookup"><span data-stu-id="d32a1-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="d32a1-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="d32a1-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d32a1-123">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d32a1-123">.NET Framework Security</span></span>  
 <span data-ttu-id="d32a1-124">Control de servicios en el equipo puede restringirse mediante el uso de la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeración para establecer permisos en el <xref:System.ServiceProcess.ServiceControllerPermission> clase.</span><span class="sxs-lookup"><span data-stu-id="d32a1-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="d32a1-125">Acceso a la información del servicio puede restringirse mediante el uso de la <xref:System.Security.Permissions.PermissionState> enumeración para establecer permisos en el <xref:System.Security.Permissions.SecurityPermission> clase.</span><span class="sxs-lookup"><span data-stu-id="d32a1-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32a1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d32a1-126">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [<span data-ttu-id="d32a1-127">Pausa de un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d32a1-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
