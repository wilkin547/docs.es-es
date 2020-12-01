---
title: Procedimiento para continuar un servicio de Windows (Visual Basic)
description: Lea cómo usar el componente ServiceController para continuar un servicio de Windows (como el Servicio de administración IIS) en un equipo local con Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
ms.openlocfilehash: 89313ebec87d154621b23b57bfa1eeda5ac3dee4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270659"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="8a615-103">Procedimiento para continuar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a615-103">How to: Continue a Windows Service (Visual Basic)</span></span>

<span data-ttu-id="8a615-104">En este ejemplo se utiliza el componente <xref:System.ServiceProcess.ServiceController> para continuar un servicio IIS Admin en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="8a615-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a615-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a615-105">Example</span></span>  

 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="8a615-106">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8a615-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="8a615-107">En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Servicios de Windows**.</span><span class="sxs-lookup"><span data-stu-id="8a615-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="8a615-108">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="8a615-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8a615-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8a615-109">Compiling the Code</span></span>  

 <span data-ttu-id="8a615-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8a615-110">This example requires:</span></span>  
  
- <span data-ttu-id="8a615-111">Una referencia de proyecto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="8a615-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="8a615-112">Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="8a615-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="8a615-113">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="8a615-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="8a615-114">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="8a615-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8a615-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8a615-115">Robust Programming</span></span>  

 <span data-ttu-id="8a615-116">De manera predeterminada, la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> de la clase <xref:System.ServiceProcess.ServiceController> es el equipo local.</span><span class="sxs-lookup"><span data-stu-id="8a615-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="8a615-117">Para hacer referencia a los servicios de Windows en otro equipo, cambie la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> al nombre de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8a615-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="8a615-118">No puede llamar al método <xref:System.ServiceProcess.ServiceController.Continue%2A> en un servicio hasta que el estado del controlador de servicio sea <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="8a615-118">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="8a615-119">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="8a615-119">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8a615-120">No se puede reanudar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8a615-120">The service cannot be resumed.</span></span> <span data-ttu-id="8a615-121">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="8a615-121">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="8a615-122">Error de acceso a la API del sistema.</span><span class="sxs-lookup"><span data-stu-id="8a615-122">An error occurred when accessing a system API.</span></span> <span data-ttu-id="8a615-123">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="8a615-123">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8a615-124">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8a615-124">.NET Framework Security</span></span>  

 <span data-ttu-id="8a615-125">El control de servicios en el equipo puede restringirse con la enumeración <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer los permisos en la clase <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="8a615-125">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="8a615-126">El acceso a la información del servicio puede restringirse con la enumeración <xref:System.Security.Permissions.PermissionState> para establecer los permisos en la clase <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="8a615-126">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a615-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a615-127">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="8a615-128">Cómo: Pausar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a615-128">How to: Pause a Windows Service (Visual Basic)</span></span>](how-to-pause-a-windows-service-visual-basic.md)
