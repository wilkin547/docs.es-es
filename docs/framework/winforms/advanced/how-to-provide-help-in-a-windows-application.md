---
title: "C&#243;mo: Proporcionar ayuda en una aplicaci&#243;n para Windows | Microsoft Docs"
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
  - "formularios, proporcionar ayuda"
  - "Ayuda, aplicaciones Windows"
  - "HelpProvider (componente) [Windows Forms]"
  - "Ayuda HTML, Windows Forms"
  - "aplicaciones Windows, proporcionar ayuda"
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Proporcionar ayuda en una aplicaci&#243;n para Windows
Puede utilizar el componente <xref:System.Windows.Forms.HelpProvider> para asociar los temas de Ayuda dentro de un archivo de Ayuda a controles específicos en los formularios Windows Forms.  El archivo de Ayuda puede ser HTML o HTMLHelp 1.x o un formato superior.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para proporcionar Ayuda  
  
1.  En el **Cuadro de herramientas**, arrastre un componente <xref:System.Windows.Forms.HelpProvider> al formulario.  
  
     El componente se colocará en la bandeja que se encuentra en la parte inferior del Diseñador de Windows Forms.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> en el archivo de Ayuda .chm, .col o .htm.  
  
3.  Seleccione otro control del formulario y establezca la propiedad [HelpKeyword](frlrfSystemWindowsFormsHelpProviderClassSetHelpKeywordTopic) en la ventana **Propiedades**.  
  
     Ésta es la cadena que se pasa al archivo de Ayuda a través del componente <xref:System.Windows.Forms.HelpProvider> para abrir el tema de Ayuda apropiado.  
  
4.  En la ventana **Propiedades**, establezca la propiedad [HelpNavigator](frlrfSystemWindowsFormsHelpProviderClassSetHelpNavigatorTopic) en un valor de la enumeración <xref:System.Windows.Forms.HelpNavigator>.  
  
     Esto determina de qué forma se pasa la propiedad **HelpKeyword** al sistema de Ayuda.  En la tabla siguiente se muestra la posible configuración y sus descripciones.  
  
    |Nombre de miembro|Descripción|  
    |-----------------------|-----------------|  
    |AssociateIndex|Especifica que el índice de un tema concreto se ejecuta en la dirección URL determinada.|  
    |Find|Especifica que se muestra la página de búsqueda de una dirección URL determinada.|  
    |Índice|Especifica que se muestra el índice de una dirección URL determinada.|  
    |KeywordIndex|Especifica una palabra clave para buscar y la acción que debe ejecutarse en la dirección URL determinada.|  
    |TableOfContents|Especifica que se muestra la tabla de contenido del archivo de Ayuda HTML 1.0.|  
    |Tema|Especifica que se muestra el tema al que hace referencia la dirección URL determinada.|  
  
 En tiempo de ejecución, si se presiona F1 cuando el control \(para el cual se han establecido las propiedades **HelpKeyword**  y **HelpNavigator** \) tiene el foco, se abrirá el archivo de Ayuda con el que está asociado ese componente <xref:System.Windows.Forms.HelpProvider>.  
  
 Actualmente, la propiedad **HelpNamespace** admite archivos de Ayuda en los formatos HTMLHelp 1.x, HTMLHelp 2.0 y HTML.  Por tanto, se puede establecer la propiedad **HelpNamespace** en una dirección http:\/\/, por ejemplo, una página Web.  Si esto se realiza, abrirá el explorador predeterminado en la página Web con la cadena especificada en la propiedad **HelpKeyword** utilizada como delimitador.  El delimitador se utiliza para saltar a una parte determinada de una página HTML.  
  
> [!IMPORTANT]
>  Tenga cuidado de comprobar cualquier información que se envíe desde un cliente antes de utilizarla en la aplicación.  Usuarios malintencionados podrían enviar o inyectar script ejecutable, instrucciones de SQL u otro código.  Antes de mostrar los datos facilitados por un usuario, almacenarlos en una base de datos o trabajar con ellos, compruebe que no contienen información potencialmente insegura.  Una manera típica de comprobarlo es utilizar una expresión regular para buscar palabras clave como "SCRIPT" cuando reciba información facilitada por un usuario.  
  
 Tenga en cuanta que se puede también utilizar el componente <xref:System.Windows.Forms.HelpProvider> para mostrar la Ayuda emergente, aunque esté configurado para mostrar archivos de Ayuda para los controles de los formularios Windows Forms.  Para obtener más información, vea [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## Vea también  
 [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)   
 [Controlar la ayuda mediante información sobre herramientas](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Integrar la Ayuda de usuario en formularios Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)