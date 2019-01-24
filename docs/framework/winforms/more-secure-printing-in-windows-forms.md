---
title: Impresión más segura en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 2bf05461014c3511725cb28caf2de0eb4c2e1d5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621804"
---
# <a name="more-secure-printing-in-windows-forms"></a>Impresión más segura en formularios Windows Forms
Las aplicaciones de Windows Forms con frecuencia incluyen la capacidad de impresión. El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] usa el <xref:System.Drawing.Printing.PrintingPermission> clase para controlar el acceso a las capacidades de impresión y asociado <xref:System.Drawing.Printing.PrintingPermissionLevel> valor de enumeración para indicar el nivel de acceso. De forma predeterminada, está habilitada la impresión de forma predeterminada en las zonas de Intranet Local e Internet; Sin embargo, el nivel de acceso está restringido en ambas zonas. Si la aplicación pueda imprimir, requiere la intervención del usuario, o no pueda imprimir depende el valor de permiso concedido a la aplicación. De forma predeterminada, la zona Intranet Local recibe <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> recibe acceso y la zona de Intranet <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> acceso.  
  
 En la tabla siguiente se muestra la funcionalidad disponible en cada nivel de permiso de impresión.  
  
|PrintingPermissionLevel|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Proporciona acceso completo a todas las impresoras instaladas.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Permite la impresión mediante programación a la impresora predeterminada y una impresión más segura a través de un cuadro de diálogo de impresión restrictivo. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Proporciona impresión únicamente desde un cuadro de diálogo más restringido. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Impide el acceso a las impresoras. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Vea también
- [Acceso más seguro a archivos y datos en Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)
- [Consideraciones de seguridad adicionales en Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)
- [Información general sobre la seguridad en Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)
- [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)
