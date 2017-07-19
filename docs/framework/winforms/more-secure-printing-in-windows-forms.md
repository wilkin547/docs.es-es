---
title: "More Secure Printing in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, printing"
  - "PrintingPermission class, Windows Forms security"
  - "printing [Windows Forms], security"
  - "security [Windows Forms], printing"
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# More Secure Printing in Windows Forms
Las aplicaciones de Windows Forms con frecuencia incluyen capacidad de impresión.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] utiliza la clase <xref:System.Drawing.Printing.PrintingPermission> para controlar el acceso a las funciones de impresión y el valor de enumeración <xref:System.Drawing.Printing.PrintingPermissionLevel> asociado para indicar el nivel de acceso.  De manera predeterminada, la impresión está habilitada en las zonas Intranet local e Internet; sin embargo, el nivel de acceso está limitado en ambas zonas.  Que la aplicación pueda imprimir, que requiera intervención del usuario o que no pueda imprimir depende de los permisos que se hayan concedido a la aplicación.  De manera predeterminada, la zona Intranet local recibe el acceso <xref:System.Drawing.Printing.PrintingPermissionLevel> y la zona Intranet recibe el acceso <xref:System.Drawing.Printing.PrintingPermissionLevel>.  
  
 La tabla siguiente muestra la funcionalidad disponible en cada nivel de permisos de impresión.  
  
|PrintingPermissionLevel|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Proporciona acceso completo a todas las impresoras instaladas.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Permite la impresión mediante programación en la impresora predeterminada y la impresión más segura a través de un cuadro de diálogo de impresión restrictivo.  <xref:System.Drawing.Printing.PrintingPermissionLevel> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Proporciona impresión únicamente desde un cuadro de diálogo más restringido.  <xref:System.Drawing.Printing.PrintingPermissionLevel> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Impide el acceso a las impresoras.  <xref:System.Drawing.Printing.PrintingPermissionLevel> es un subconjunto de <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
  
## Vea también  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Additional Security Considerations in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)   
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)