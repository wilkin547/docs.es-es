---
title: "Additional Security Considerations in Windows Forms | Microsoft Docs"
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
  - "Windows API, secure calls"
  - "Windows Forms, secure calls to Windows API"
  - "Windows API, calling"
  - "APIs, calling"
  - "security [Windows Forms]"
  - "Windows API, Windows Forms security settings"
  - "API calls, Windows Forms security settings"
  - "security [Windows Forms], calling APIs"
  - "Clipboard, securing access"
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Additional Security Considerations in Windows Forms
La configuración de seguridad de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] puede hacer que la aplicación se ejecute de manera diferente en un entorno de confianza parcial que en el equipo local.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] restringe el acceso a recursos locales críticos como el sistema de archivos, la red y API no administradas, entre otras cosas.  La configuración de seguridad afecta a la capacidad de llamar a la API Microsoft Win32 u otras API que no pueda comprobar el sistema de seguridad.  La seguridad afecta también a otros aspectos de la aplicación, incluido el acceso a archivos y datos y su impresión.  Para obtener más información sobre el acceso a archivos y datos en un entorno de confianza parcial, vea [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md).  Para obtener más información sobre cómo imprimir en un entorno de confianza parcial, vea [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md).  
  
 Las siguientes secciones explican cómo trabajar con el Portapapeles, manipular ventanas y llamar a la API Win32 desde aplicaciones que se ejecutan en un entorno de confianza parcial.  
  
## Acceso al Portapapeles  
 La clase <xref:System.Security.Permissions.UIPermission> controla el acceso al Portapapeles y el valor de enumeración <xref:System.Security.Permissions.UIPermissionClipboard> asociado indica el nivel de acceso.  La tabla siguiente muestra los niveles de permiso posibles.  
  
|Valor UIPermissionClipboard|Descripción|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Se puede utilizar el Portapapeles sin límites.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Se puede utilizar el Portapapeles con ciertas limitaciones.  La capacidad de colocar datos en el Portapapeles \(operaciones del comando Copiar o Cortar\) no está limitada.  Los controles intrínsecos que acepten Pegar, como un cuadro de texto, pueden aceptar datos del Portapapeles, pero los controles de usuario no pueden leer el Portapapeles mediante programación.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|No se puede utilizar el Portapapeles.|  
  
 De manera predeterminada, la zona Intranet local recibe el acceso <xref:System.Security.Permissions.UIPermissionClipboard> y la zona Internet recibe el acceso <xref:System.Security.Permissions.UIPermissionClipboard>.  Esto significa que la aplicación puede copiar datos en el Portapapeles, pero no puede leer el Portapapeles ni pegar datos en él mediante programación.  Estas limitaciones impiden que los programas que no sean de plena confianza lean el contenido copiado en el Portapapeles por otra aplicación.  Si la aplicación requiere acceso total al Portapapeles pero no tiene los permisos necesarios, deberá conceder dichos permisos a la aplicación.  Para obtener más información sobre la concesión de permisos, vea [Administración de la directiva de seguridad general](http://msdn.microsoft.com/es-es/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## Manipulación de ventanas  
 La clase <xref:System.Security.Permissions.UIPermission> controla también el permiso para manipular ventanas y otras acciones relacionadas con la interfaz de usuario, y el valor de enumeración <xref:System.Security.Permissions.UIPermissionWindow> asociado indica el nivel de acceso.  La tabla siguiente muestra los niveles de permiso posibles.  
  
 De manera predeterminada, la zona Intranet local recibe el acceso <xref:System.Security.Permissions.UIPermissionWindow> y la zona Internet recibe el acceso <xref:System.Security.Permissions.UIPermissionWindow>.  Esto significa que, en la zona Internet, la aplicación puede realizar la mayoría de las operaciones de ventanas de la interfaz de usuario, pero se modificará la apariencia de la ventana.  La ventana modificada muestra una notificación en un globo la primera vez que se ejecuta, contiene el texto de la barra de título modificada y requiere un botón Cerrar en la barra de título.  La notificación del globo y la barra de título informan al usuario de la aplicación que ésta se está ejecutando bajo confianza parcial.  
  
|Valor UIPermissionWindow|Descripción|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Los usuarios pueden utilizar todas las ventanas y eventos de entrada de usuario sin restricciones.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Los usuarios sólo pueden utilizar ventanas de nivel superior y subventanas más seguras para dibujar, y sólo pueden utilizar eventos de entrada de datos proporcionados por el usuario para la interfaz de usuario dentro de dichas ventanas y subventanas de nivel superior.  Estas ventanas más seguras están claramente etiquetadas y tienen límites de tamaño máximo y mínimo.  Las restricciones evitan posibles ataques de suplantación peligrosos, como la imitación de las pantallas de inicio de sesión en el sistema o del escritorio del sistema, y limitan el acceso mediante programación a las ventanas primarias, a las API relacionadas con el foco y el uso del control <xref:System.Windows.Forms.ToolTip>|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Los usuarios sólo pueden utilizar subventanas más seguras para dibujar, y sólo pueden utilizar eventos de entrada de datos por el usuario para la interfaz de usuario dentro de esa subventana.  Un control mostrado en un explorador es un ejemplo de una subventana más segura.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Los usuarios no pueden utilizar ninguna ventana ni ningún evento de interfaz de usuario.  No se puede utilizar ninguna interfaz de usuario.|  
  
 Cada nivel de permiso identificado por la enumeración <xref:System.Security.Permissions.UIPermissionWindow> permite menos acciones que su nivel superior.  Las tablas siguientes indican las acciones que restringen los valores <xref:System.Security.Permissions.UIPermissionWindow> y <xref:System.Security.Permissions.UIPermissionWindow>.  Para saber los permisos exactos necesarios para cada miembro, consulte el material de referencia de dicho miembro en la documentación de la biblioteca de clases de .NET Framework.  
  
 El permiso <xref:System.Security.Permissions.UIPermissionWindow> limita las acciones enumeradas en la siguiente tabla.  
  
|Componente|Acciones restringidas|  
|----------------|---------------------------|  
|<xref:System.Windows.Forms.Application>|-   Configurar la propiedad <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-   Obtener la propiedad <xref:System.Windows.Forms.Control.Parent%2A>.<br />-   Configurar la propiedad `Region`.<br />-   Llamar a los métodos <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> y <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A> o <xref:System.Windows.Forms.Control.SetTopLevel%2A>.<br />-   Llamar al método <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> si el control devuelto no es secundario del control que llama.<br />-   Modifique el foco en el control contenedor.|  
|<xref:System.Windows.Forms.Cursor>|-   Configurar la propiedad <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-   Llamar al método <xref:System.Windows.Forms.Control.Hide%2A>.|  
|<xref:System.Windows.Forms.DataGrid>|-   Llamar al método <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A>.|  
|<xref:System.Windows.Forms.Form>|-   Obtener la propiedad <xref:System.Windows.Forms.Form.ActiveForm%2A> o <xref:System.Windows.Forms.Form.MdiParent%2A>.<br />-   Configurar la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A> o <xref:System.Windows.Forms.Form.TopMost%2A>.<br />-   Configurar la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> por debajo del 50%.<br />-   Establecer la propiedad <xref:System.Windows.Forms.Form.WindowState%2A> en <xref:System.Windows.Forms.FormWindowState> mediante programación.<br />-   Llamar al método <xref:System.Windows.Forms.Form.Activate%2A>.<br />-   Utilizar los valores de enumeración <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> y <xref:System.Windows.Forms.FormBorderStyle><xref:System.Windows.Forms.FormBorderStyle>.|  
|<xref:System.Windows.Forms.NotifyIcon>|-   El uso del componente <xref:System.Windows.Forms.NotifyIcon> está totalmente restringido.|  
  
 El valor <xref:System.Security.Permissions.UIPermissionWindow> restringe las acciones enumeradas en la siguiente tabla, además de las limitaciones que impone el valor <xref:System.Security.Permissions.UIPermissionWindow>.  
  
|Componente|Acciones restringidas|  
|----------------|---------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-   Mostrar un cuadro de diálogo derivado de la clase <xref:System.Windows.Forms.CommonDialog>.|  
|<xref:System.Windows.Forms.Control>|-   Llamar al método <xref:System.Windows.Forms.Control.CreateGraphics%2A>.<br />-   Configurar la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Configurar la propiedad <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-   Llamar al método <xref:System.Windows.Forms.Form.Show%2A>.|  
  
### Hospedar controles de otro fabricante  
 Otro tipo de manipulación de ventanas es posible si los formularios hospedan controles de otro fabricante.  Un control de otro fabricante es cualquier <xref:System.Windows.Forms.UserControl> personalizado que no ha desarrollado y compilado usted mismo.  Aunque el escenario de hospedaje es difícil de manipular, teóricamente es posible que un control de otro fabricante expanda su superficie de representación para abarcar todo el área de su formulario.  Después, el control podría imitar un cuadro de diálogo crítico y solicitar información tal como una combinación de nombre de usuario y contraseña o los números de cuenta bancaria de sus usuarios.  
  
 Para limitar este riesgo potencial, utilice sólo controles de proveedores de confianza.  Si utiliza controles de otro fabricante que ha descargado de un origen que no puede comprobar, se recomienda que revise el código fuente en busca de posibles puntos vulnerables.  Después de comprobar que el origen no es malintencionado, debería compilar el ensamblado para garantizar que el origen coincide con el ensamblado.  
  
## Llamadas API Win32  
 Si el diseño de la aplicación requiere llamar a una función de la API Win32, estará teniendo acceso a código no administrado.  En este caso las acciones del código en la ventana o el sistema operativo no se pueden determinar cuando se trabaja con llamadas API o valores de Win32.  La clase <xref:System.Security.Permissions.SecurityPermission> y el valor <xref:System.Security.Permissions.SecurityPermissionFlag> del control de enumeración <xref:System.Security.Permissions.SecurityPermissionFlag> tienen acceso a código no administrado.  Una aplicación sólo puede tener acceso a código no administrado cuando tiene el permiso <xref:System.Security.Permissions.SecurityPermissionFlag>.  De manera predeterminada, sólo las aplicaciones que se ejecutan localmente pueden llamar a código no administrado.  
  
 Algunos miembros de formularios Windows Forms proporcionan acceso no administrado que requiere el permiso <xref:System.Security.Permissions.SecurityPermissionFlag>.  La siguiente tabla enumera los miembros del espacio de nombres <xref:System.Windows.Forms> que requieren el permiso.  Para obtener más información sobre los permisos necesarios para un miembro, consulte la documentación de la biblioteca de clases de .NET Framework.  
  
|Componente|Miembro|  
|----------------|-------------|  
|<xref:System.Windows.Forms.Application>|-   Método <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   Propiedad <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A><br />-   Método `Exit`<br />-   Método <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   Evento <xref:System.Windows.Forms.Application.ThreadException>|  
|<xref:System.Windows.Forms.CommonDialog>|-   Método <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   Método <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\\<br />-   Método <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />-   Método <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|-   Método <xref:System.Windows.Forms.Control.CreateParams%2A><br />-   Método <xref:System.Windows.Forms.Control.DefWndProc%2A><br />-   Método <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />-   Método <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   Métodos <xref:System.Windows.Forms.Help.ShowHelp%2A><br />-   Método <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   Clase <xref:System.Windows.Forms.NativeWindow>|  
|<xref:System.Windows.Forms.Screen>|-   Método <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|-   Método <xref:System.Windows.Forms.SendKeys.Send%2A><br />-   Método <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Si la aplicación no tiene permiso para llamar a código no administrado, tendrá que solicitar el permiso <xref:System.Security.Permissions.SecurityPermissionFlag>, o deberá considerar modos alternativos de implementar las características; en muchos casos, los formularios Windows Forms proporcionan una alternativa administrada a las funciones de la API Win32.  Si no existen ningún medio alternativo y la aplicación debe tener acceso a código no administrado, deberá conceder permisos a la aplicación.  
  
 El permiso para llamar a código no administrado permite a la aplicación realizar casi todo.  Por ello, este permiso para llamar a código no administrado únicamente se debe conceder a aplicaciones que procedan de un origen de confianza.  De forma alternativa, dependiendo de la aplicación, la función que realiza la llamada al código no administrado podría ser opcional, o sólo habilitarse en el entorno de plena confianza.  Para obtener más información sobre los permisos arriesgados, vea [Permisos peligrosos y administración de directivas](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md).  Para obtener más información sobre la elevación de permisos, vea [NIB: General Security Policy Administration](http://msdn.microsoft.com/es-es/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## Vea también  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)   
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)   
 [Proteger las aplicaciones ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md)