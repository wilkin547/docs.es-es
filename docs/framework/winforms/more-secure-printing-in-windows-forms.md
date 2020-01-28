---
title: Impresión más segura
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734883"
---
# <a name="more-secure-printing-in-windows-forms"></a>Impresión más segura en Windows Forms
Las aplicaciones Windows Forms suelen incluir capacidades de impresión. En el .NET Framework se usa la clase <xref:System.Drawing.Printing.PrintingPermission> para controlar el acceso a las funciones de impresión y el valor de enumeración <xref:System.Drawing.Printing.PrintingPermissionLevel> asociado para indicar el nivel de acceso. De forma predeterminada, la impresión está habilitada de forma predeterminada en la Intranet local y en las zonas de Internet; sin embargo, el nivel de acceso está restringido en ambas zonas. El hecho de que la aplicación pueda imprimir, requiera la interacción del usuario o no pueda imprimir depende del valor de permiso que se haya concedido a la aplicación. De forma predeterminada, la zona Intranet local recibe el acceso <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> y la zona Intranet recibe <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> acceso.  
  
 En la tabla siguiente se muestra la funcionalidad disponible en cada nivel de permiso de impresión.  
  
|PrintingPermissionLevel|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Proporciona acceso completo a todas las impresoras instaladas.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Habilita la impresión mediante programación en la impresora predeterminada y la impresión más segura a través de un cuadro de diálogo de impresión restrictiva. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Solo proporciona impresión desde un cuadro de diálogo más restringido. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Impide el acceso a las impresoras. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Vea también

- [Acceso más seguro a archivos y datos en Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Consideraciones de seguridad adicionales en Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Información general sobre la seguridad en Windows Forms](security-in-windows-forms-overview.md)
- [Windows Forms Security](windows-forms-security.md)
