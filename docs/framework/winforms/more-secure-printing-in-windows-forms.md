---
title: "Impresión más segura en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b89a94fd0223d817b0dee37f7a3ed84dcbacbbec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="0d764-102">Impresión más segura en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d764-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="0d764-103">Aplicaciones de Windows Forms con frecuencia incluyen capacidad de impresión.</span><span class="sxs-lookup"><span data-stu-id="0d764-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="0d764-104">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] utiliza la <xref:System.Drawing.Printing.PrintingPermission> clase para controlar el acceso a capacidades de impresión y asociado <xref:System.Drawing.Printing.PrintingPermissionLevel> valor de enumeración para indicar el nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="0d764-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="0d764-105">De forma predeterminada, está habilitada la impresión de forma predeterminada en las zonas de Intranet Local e Internet; Sin embargo, el nivel de acceso está restringido en ambas zonas.</span><span class="sxs-lookup"><span data-stu-id="0d764-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="0d764-106">Si la aplicación pueda imprimir, requiere la intervención del usuario, o no pueda imprimir depende del valor del permiso concedido a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d764-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="0d764-107">De forma predeterminada, la zona Intranet Local recibe <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> recibe acceso y la zona de Intranet <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> acceso.</span><span class="sxs-lookup"><span data-stu-id="0d764-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="0d764-108">En la tabla siguiente se muestra la funcionalidad disponible en cada nivel de permiso de impresión.</span><span class="sxs-lookup"><span data-stu-id="0d764-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="0d764-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="0d764-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="0d764-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d764-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="0d764-111">Proporciona acceso completo a todas las impresoras instaladas.</span><span class="sxs-lookup"><span data-stu-id="0d764-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="0d764-112">Permite imprimir mediante programación a la impresora predeterminada y una impresión más segura a través de un cuadro de diálogo de impresión restrictivo.</span><span class="sxs-lookup"><span data-stu-id="0d764-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="0d764-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span><span class="sxs-lookup"><span data-stu-id="0d764-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="0d764-114">Proporciona impresión únicamente desde un cuadro de diálogo más restringido.</span><span class="sxs-lookup"><span data-stu-id="0d764-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="0d764-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span><span class="sxs-lookup"><span data-stu-id="0d764-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="0d764-116">Impide el acceso a las impresoras.</span><span class="sxs-lookup"><span data-stu-id="0d764-116">Prevents access to printers.</span></span> <span data-ttu-id="0d764-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span><span class="sxs-lookup"><span data-stu-id="0d764-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d764-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d764-118">See Also</span></span>  
 [<span data-ttu-id="0d764-119">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d764-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="0d764-120">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d764-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="0d764-121">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d764-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="0d764-122">Windows Forms Security</span><span class="sxs-lookup"><span data-stu-id="0d764-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
