---
title: "Cómo: Proporcionar ayuda en una aplicación para Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f407f1c17c67ec99f4499b89c49932a4ba6d32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Cómo: Proporcionar ayuda en una aplicación para Windows
Puede usar de la <xref:System.Windows.Forms.HelpProvider> componente para asociar los temas de ayuda dentro de un archivo de ayuda a controles específicos en formularios Windows Forms. El archivo de ayuda puede ser HTML, HTMLHelp 1.x o superior.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-provide-help"></a>Para proporcionar ayuda  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.HelpProvider> al formulario.  
  
     El componente estará en la bandeja, en la parte inferior del Diseñador de Windows Forms.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad al archivo de ayuda .chm, .col o. htm.  
  
3.  Seleccione otro control tiene en el formulario y, en la **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> propiedad.  
  
     Se trata de la cadena que se pasa a través de la <xref:System.Windows.Forms.HelpProvider> componente al archivo de ayuda para abrir el tema de Ayuda apropiado.  
  
4.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> en un valor de la <xref:System.Windows.Forms.HelpNavigator> enumeración.  
  
     Esto determina la forma en la que la propiedad **HelpKeyword** pasa al sistema de ayuda. La siguiente tabla muestra los valores posibles y sus descripciones.  
  
    |Nombre de miembro|Descripción|  
    |-----------------|-----------------|  
    |AssociateIndex|Especifica que el índice de un tema determinado se realiza en la dirección URL especificada.|  
    |Find|Especifica que se muestre la página de búsqueda de una dirección URL especificada.|  
    |Índice|Especifica que se muestre el índice de una dirección URL especificada.|  
    |KeywordIndex|Especifica una palabra clave que buscar y la acción que se realizará en la dirección URL especificada.|  
    |TableOfContents|Especifica que se muestra la tabla de contenidos del archivo de ayuda HTML 1.0.|  
    |Tema|Especifica que se muestra el tema al que hace referencia la dirección URL especificada.|  
  
 En tiempo de ejecución, al presionar F1 cuando el control, para que ha establecido la **HelpKeyword** y **HelpNavigator** propiedades: tiene foco abrirá el archivo de ayuda asociados a ese <xref:System.Windows.Forms.HelpProvider> componente.  
  
 Actualmente, la propiedad **HelpNamespace** admite archivos de ayuda en los tres formatos siguientes: HTMLHelp 1.x, HTMLHelp 2.0 y HTML. Por lo tanto, puede establecer la propiedad **HelpNamespace** en una dirección http://, como una página web. Si esto sucede, se abrirá el explorador predeterminado en la página web con la cadena especificada en la propiedad **HelpKeyword** utilizada como delimitador. El delimitador se utiliza para saltar a una parte específica de una página HTML.  
  
> [!IMPORTANT]
>  Tenga cuidado de comprobar cualquier información que se envíe desde un cliente antes de utilizarla en su aplicación. Los usuarios malintencionados podrían intentar enviar o inyectar scripts ejecutables, instrucciones SQL u otro código. Antes de mostrar la entrada del usuario, almacénela en una base de datos o trabaje con ella, y compruebe que no contiene información potencialmente insegura. Una forma habitual de comprobación es utilizar una expresión regular para buscar palabras clave como "SCRIPT" cuando se recibe la entrada de un usuario.  
  
 También puede usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente, aunque se haya configurado para mostrar archivos de ayuda para los controles en los formularios Windows Forms. Para más información, consulte [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## <a name="see-also"></a>Vea también  
 [Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [Controlar la ayuda mediante componentes Tooltip](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrar la Ayuda de usuario en Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
