---
title: "Consideraciones al alojar un control ActiveX en Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles ActiveX [Windows Forms], agregar"
  - "controles ActiveX [Windows Forms], hospedaje"
  - "controles de Windows Forms, controles ActiveX"
  - "Windows Forms, controles ActiveX"
  - "Windows Forms, hospedar controles ActiveX"
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Consideraciones al alojar un control ActiveX en Windows Forms
Aunque los formularios Windows Forms se han optimizado para que hospeden controles de formularios Windows Forms, puede seguir utilizando controles ActiveX.  No olvide las consideraciones siguientes al planear una aplicación que utilice controles ActiveX:  
  
-   **Seguridad** En Common Language Runtime se ha mejorado la seguridad de acceso del código.  Las aplicaciones que incluyen formularios Windows Forms pueden ejecutarse en un entorno de seguridad total sin ningún problema y en un entorno de seguridad parcial con accesibilidad a la mayor parte de su funcionalidad.  Los controles de formularios Windows Forms pueden hospedarse en un explorador sin ninguna complicación.  Sin embargo, los controles ActiveX no pueden aprovechar estas mejoras de seguridad en formularios Windows Forms.  La ejecución de control ActiveX requiere un permiso de código no administrado, que se establece con la propiedad <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=fullName>.  Para obtener más información sobre la seguridad y el permiso para utilizar código no administrado, vea la clase [SecurityPermissionAttribute](frlrfSystemSecurityPermissionsSecurityPermissionAttributeClassTopic).  
  
-   **Costo total de propiedad** Cualquier control ActiveX agregado a un Windows Form se implementa con el formulario completo, con lo que puede aumentar significativamente el tamaño de los archivos creados.  Además, el uso de controles ActiveX en formularios Windows Forms requiere que se escriba en el Registro.  Esto supone un mayor grado de intrusión para el equipo de un usuario que los controles de formularios Windows Forms, que no necesitan esta acción.  
  
    > [!NOTE]
    >  Trabajar con un control ActiveX requiere el uso de un contenedor de interoperabilidad COM.  Para obtener más información, vea [Interoperabilidad COM en Visual Basic y Visual C\#](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md).  
  
    > [!NOTE]
    >  Si el nombre de un miembro de un control ActiveX coincide con un nombre definido en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], el Importador de controles ActiveX agregará el prefijo **Ctl** al nombre del miembro cuando cree la clase derivada <xref:System.Windows.Forms.AxHost>.  Por ejemplo, si el control ActiveX tiene un miembro denominado **Layout**, se le cambia el nombre a **CtlLayout** en la clase derivada de AxHost, porque el evento **Layout** está definido en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## Vea también  
 [Cómo: Agregar controles ActiveX a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Code Access Security](../../../../docs/framework/misc/code-access-security.md)   
 [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](http://msdn.microsoft.com/es-es/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Insertar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)