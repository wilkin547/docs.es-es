---
title: Procedimiento para pausar un servicio de Windows (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 166eda4a9348188fa6e5048fd3ce41645cde4816
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053598"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="e1f1f-102">Procedimiento para pausar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1f1f-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="e1f1f-103">En este ejemplo se utiliza el componente <xref:System.ServiceProcess.ServiceController> para pausar un servicio IIS Admin en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f1f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1f1f-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="e1f1f-105">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e1f1f-106">En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Servicios de Windows**.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="e1f1f-107">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e1f1f-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1f1f-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e1f1f-108">Compiling the Code</span></span>  
 <span data-ttu-id="e1f1f-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e1f1f-109">This example requires:</span></span>  
  
- <span data-ttu-id="e1f1f-110">Una referencia de proyecto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="e1f1f-111">Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="e1f1f-112">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="e1f1f-113">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="e1f1f-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e1f1f-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e1f1f-114">Robust Programming</span></span>  
 <span data-ttu-id="e1f1f-115">De manera predeterminada, la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> de la clase <xref:System.ServiceProcess.ServiceController> es el equipo local.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="e1f1f-116">Para hacer referencia a los servicios de Windows en otro equipo, cambie la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> al nombre de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="e1f1f-117">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="e1f1f-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e1f1f-118">No se puede pausar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-118">The service cannot be paused.</span></span> <span data-ttu-id="e1f1f-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="e1f1f-119">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="e1f1f-120">Error de acceso a la API del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="e1f1f-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="e1f1f-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e1f1f-122">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1f1f-122">.NET Framework Security</span></span>  
 <span data-ttu-id="e1f1f-123">El control de servicios en el equipo puede restringirse con <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer los permisos en <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="e1f1f-124">El acceso a la información del servicio puede restringirse con <xref:System.Security.Permissions.PermissionState> para establecer los permisos en <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="e1f1f-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f1f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f1f-125">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="e1f1f-126">Cómo: Continuar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1f1f-126">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
