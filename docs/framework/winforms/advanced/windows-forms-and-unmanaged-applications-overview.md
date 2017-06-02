---
title: "Informaci&#243;n general sobre formularios Windows Forms y aplicaciones no administradas | Microsoft Docs"
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
  - "COM [Windows Forms]"
  - "Windows Forms, sin administrar"
  - "Interoperabilidad COM"
  - "controles ActiveX [Windows Forms], acerca de los controles ActiveX"
  - "Windows Forms, interoperabilidad"
ms.assetid: 0a26d99d-8135-4895-8760-c9a2b5f67f14
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre formularios Windows Forms y aplicaciones no administradas
Los controles y aplicaciones de Windows Forms pueden interoperar con aplicaciones no administradas, con algunas advertencias. En las secciones siguientes se describen los escenarios y las configuraciones que las aplicaciones y los controles de Windows Forms admiten y no admiten.  
  
## Aplicaciones ActiveX y controles de Windows Forms  
 Con la excepción de Microsoft Internet Explorer y Microsoft Foundation Classes \(MFC\), los controles de Windows Forms no se admiten en aplicaciones diseñadas para hospedar controles ActiveX. Otras aplicaciones y herramientas de desarrollo que pueden hospedar controles ActiveX, incluidos los contenedores de prueba de ActiveX de versiones de Visual Studio anteriores a Visual Studio .NET 2003, no son hosts admitidos para controles de Windows Forms.  
  
 Estas restricciones también se aplican al uso de controles de Windows Forms mediante la interoperabilidad del Modelo de objetos componentes \(COM\). El uso de controles de Windows Forms mediante un contenedor COM invocable \(CCW\) solo se admite en Internet Explorer. Para obtener más información sobre la interoperabilidad COM, consulte  
  
 [Interoperabilidad COM](../Topic/COM%20Interop%20\(Visual%20Basic\).md).  
  
 En la siguiente tabla se muestra que hosts ActiveX admiten controles de Windows Forms.  
  
|Versión de Windows Forms|Compatibilidad|  
|------------------------------|--------------------|  
|.NET Framework versión 1.0|Internet Explorer 5.01 y versiones posteriores|  
|.NET framework versión 1.1 y versiones posteriores|Internet Explorer 5.01 y versiones posteriores<br /><br /> Microsoft Foundation Classes \(MFC\) 7.0 y versiones posteriores|  
  
## Hospedaje de componentes de Windows Forms como controles ActiveX  
 En .NET Framework 1.1, se amplió la compatibilidad para incluir MFC 7.0 y versiones posteriores. Esta compatibilidad incluye cualquier contenedor que sea totalmente compatible con el contenedor de controles ActiveX de MFC 7.0 y versiones posteriores.  
  
 Sin embargo, no se permite registrar controles de Windows Forms como controles ActiveX. Tampoco se permite llamar al método `com.ms.win32.Ole32.CoCreateInstance` para los controles de Windows Forms. Solo se permite la activación administrada de controles de Windows Forms. Una vez creado un control de Windows Forms, puede hospedarlo en una aplicación MFC igual que haría con un control ActiveX.  
  
 Para usar controles de Windows Forms en la aplicación no administrada, debe hospedar el CLR usando las API de hospedaje de CLR no administradas o usando las características de interoperabilidad de C\+\+. El procedimiento recomendado es usar las características de interoperabilidad de C\+\+.  
  
## Windows Forms en aplicaciones cliente COM.  
 Al abrir un Windows Form con una aplicación cliente COM, por ejemplo, una aplicación de Visual Basic 6.0 o una aplicación MFC, el formulario puede tener un comportamiento inesperado. Por ejemplo, al presionar la tecla TAB, el foco no cambia de un control a otro. Al presionar la tecla ENTRAR cuando un botón de comando tiene el foco, no se produce el evento <xref:System.Windows.Forms.Control.Click> del botón. También puede experimentar un comportamiento inesperado de las pulsaciones de teclas o de la actividad del mouse.  
  
 Este comportamiento se produce porque la aplicación no administrada no implementa la compatibilidad con el bucle de mensajes que Windows Forms necesita para funcionar correctamente. El bucle de mensajes proporcionado por la aplicación cliente COM es diferente del bucle de mensajes de Windows Forms.  
  
 El bucle de mensajes de una aplicación en un bucle de programa interno que recupera los mensajes de una cola de mensajes del subproceso, los traduce y, después, los envía a la aplicación para que los controle. El bucle de mensajes de un Windows Form no tiene la misma arquitectura que los bucles de mensajes que proporcionan aplicaciones anteriores, como las aplicaciones de Visual Basic 6.0 y las aplicaciones MFC. Es posible que los mensajes de ventana que se publican en el bucle de mensajes se controlen de una forma diferente a la que espera el Windows Form. Por lo tanto, se puede producir un comportamiento inesperado. Puede que algunas combinaciones de teclas no funcionen, que alguna actividad del mouse no funcione o que algunos eventos no se generen como se esperaba.  
  
## Resolver problemas de interoperabilidad  
 Puede resolver estos problemas mostrando el formulario en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que se crea con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>.  
  
 Para que un Windows Form funcione correctamente con una aplicación cliente COM, debe ejecutarlo en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:  
  
-   Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> para mostrar el Windows Form. Para obtener más información, consulta [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Muestre cada Windows Form en un nuevo subproceso. Para obtener más información, consulta [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## Vea también  
 [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)   
 [Interoperabilidad COM](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [Interoperabilidad COM en aplicaciones .NET Framework](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)   
 [COM Interoperability Samples](http://msdn.microsoft.com/es-es/09c38567-6380-4d70-848a-e896a4ca05f4)   
 [Aximp.exe \(Windows Forms ActiveX Control Importer\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)   
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)   
 [Registering Assemblies with COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)   
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)