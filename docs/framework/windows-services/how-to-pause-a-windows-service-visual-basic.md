---
title: Procedimiento para pausar un servicio de Windows (Visual Basic)
description: Lea cómo usar el componente ServiceController para pausar un servicio de Windows (como el Servicio de administración IIS) en un equipo local con Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
ms.openlocfilehash: 19919a8b0a289f0e88eb136d8c010a036e84cbec
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608509"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="81375-103">Procedimiento para pausar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81375-103">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="81375-104">En este ejemplo se utiliza el componente <xref:System.ServiceProcess.ServiceController> para pausar un servicio IIS Admin en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="81375-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81375-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81375-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="81375-106">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="81375-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="81375-107">En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Servicios de Windows**.</span><span class="sxs-lookup"><span data-stu-id="81375-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="81375-108">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="81375-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81375-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="81375-109">Compiling the Code</span></span>  
 <span data-ttu-id="81375-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="81375-110">This example requires:</span></span>  
  
- <span data-ttu-id="81375-111">Una referencia de proyecto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="81375-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="81375-112">Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="81375-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="81375-113">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="81375-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="81375-114">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="81375-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="81375-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="81375-115">Robust Programming</span></span>  
 <span data-ttu-id="81375-116">De manera predeterminada, la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> de la clase <xref:System.ServiceProcess.ServiceController> es el equipo local.</span><span class="sxs-lookup"><span data-stu-id="81375-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="81375-117">Para hacer referencia a los servicios de Windows en otro equipo, cambie la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> al nombre de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="81375-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="81375-118">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="81375-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="81375-119">No se puede pausar el servicio.</span><span class="sxs-lookup"><span data-stu-id="81375-119">The service cannot be paused.</span></span> <span data-ttu-id="81375-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="81375-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="81375-121">Error de acceso a la API del sistema.</span><span class="sxs-lookup"><span data-stu-id="81375-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="81375-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="81375-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="81375-123">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="81375-123">.NET Framework Security</span></span>  
 <span data-ttu-id="81375-124">El control de servicios en el equipo puede restringirse con <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer los permisos en <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="81375-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="81375-125">El acceso a la información del servicio puede restringirse con <xref:System.Security.Permissions.PermissionState> para establecer los permisos en <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="81375-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81375-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="81375-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="81375-127">Cómo: Continuar un servicio de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81375-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
