---
title: Consideraciones al alojar un control ActiveX en Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ec828ca0b2bd8231d0baca72bf97bef566f2651
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="42134-102">Consideraciones al alojar un control ActiveX en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42134-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="42134-103">Aunque Windows Forms se han optimizado para hospedar controles de Windows Forms, todavía puede utilizar los controles ActiveX.</span><span class="sxs-lookup"><span data-stu-id="42134-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="42134-104">Tenga en cuenta las consideraciones siguientes al planear una aplicación que utiliza controles ActiveX:</span><span class="sxs-lookup"><span data-stu-id="42134-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
-   <span data-ttu-id="42134-105">**Seguridad** Se ha mejorado Common Language Runtime con respecto a la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="42134-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="42134-106">Las aplicaciones que incluyen Windows Forms pueden ejecutarse en un entorno de plena confianza sin problema y en un entorno de confianza parcial con la mayoría de la funcionalidad accesible.</span><span class="sxs-lookup"><span data-stu-id="42134-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="42134-107">Los controles de Windows Forms se pueden hospedar en un explorador sin ninguna complicación.</span><span class="sxs-lookup"><span data-stu-id="42134-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="42134-108">Sin embargo, los controles ActiveX en Windows Forms no pueden aprovechar estas mejoras de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42134-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="42134-109">Ejecución de un control ActiveX requiere un permiso de código no administrado, que se establece con el <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="42134-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="42134-110">Para obtener más información sobre seguridad y el permiso de código no administrado, consulte <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="42134-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
-   <span data-ttu-id="42134-111">**Costo total de propiedad** Los controles ActiveX agregados a Windows Forms se implementan con ese formulario Windows Forms en su totalidad, lo que puede aumentar significativamente el tamaño de los archivos creados.</span><span class="sxs-lookup"><span data-stu-id="42134-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="42134-112">Además, el uso de los controles ActiveX en Windows Forms requiere que se escriba en el registro.</span><span class="sxs-lookup"><span data-stu-id="42134-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="42134-113">Esto es más invasor para un equipo de usuario que los controles de Windows Forms, que no lo necesitan.</span><span class="sxs-lookup"><span data-stu-id="42134-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42134-114">Trabajar con un control ActiveX requiere el uso de un contenedor de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="42134-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="42134-115">Para más información, consulte [Interoperabilidad COM en Visual Basic y Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="42134-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42134-116">Si el nombre de un miembro del control ActiveX coincide con un nombre definido en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], a continuación, el importador de controles ActiveX agregará el prefijo del nombre de miembro con **Ctl** cuando crea el <xref:System.Windows.Forms.AxHost> clase derivada.</span><span class="sxs-lookup"><span data-stu-id="42134-116">If the name of a member of the ActiveX control matches a name defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="42134-117">Por ejemplo, si el control ActiveX tiene un miembro denominado **Layout**, el nombre de este se cambia a **CtlLayout** en la clase derivada AxHost porque el evento **Layout** está definido en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42134-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42134-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42134-118">See Also</span></span>  
 [<span data-ttu-id="42134-119">Procedimiento para agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42134-119">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="42134-120">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="42134-120">Code Access Security</span></span>](../../../../docs/framework/misc/code-access-security.md)  
 [<span data-ttu-id="42134-121">Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas</span><span class="sxs-lookup"><span data-stu-id="42134-121">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="42134-122">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42134-122">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="42134-123">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42134-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
