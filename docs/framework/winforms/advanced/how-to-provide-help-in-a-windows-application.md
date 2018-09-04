---
title: 'Cómo: Proporcionar ayuda en una aplicación para Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 98ed6d4e10d0eb80b99a36172980fcb33186c8ca
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561875"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Cómo: Proporcionar ayuda en una aplicación para Windows
Puede usar de la <xref:System.Windows.Forms.HelpProvider> componente para asociar los temas de ayuda dentro de un archivo de ayuda a controles específicos en los formularios de Windows. El archivo de ayuda puede ser HTML, HTMLHelp 1.x o superior.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-provide-help"></a>Para proporcionar ayuda  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.HelpProvider> al formulario.  
  
     El componente estará en la bandeja, en la parte inferior del Diseñador de Windows Forms.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad al archivo de ayuda .chm, .col o. htm.  
  
3.  Seleccione otro control que tiene en su formulario y, en el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> propiedad.  
  
     Se trata de la cadena pasada a través de la <xref:System.Windows.Forms.HelpProvider> componente al archivo de ayuda para abrir el tema de Ayuda adecuado.  
  
4.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> propiedad con un valor de la <xref:System.Windows.Forms.HelpNavigator> enumeración.  
  
     Esto determina la forma en la que la propiedad **HelpKeyword** pasa al sistema de ayuda. La siguiente tabla muestra los valores posibles y sus descripciones.  
  
    |Nombre de miembro|Descripción|  
    |-----------------|-----------------|  
    |AssociateIndex|Especifica que el índice de un tema determinado se realiza en la dirección URL especificada.|  
    |Find|Especifica que se muestre la página de búsqueda de una dirección URL especificada.|  
    |Índice|Especifica que se muestre el índice de una dirección URL especificada.|  
    |KeywordIndex|Especifica una palabra clave que buscar y la acción que se realizará en la dirección URL especificada.|  
    |TableOfContents|Especifica que se muestra la tabla de contenidos del archivo de ayuda HTML 1.0.|  
    |Tema|Especifica que se muestra el tema al que hace referencia la dirección URL especificada.|  
  
 En tiempo de ejecución, al presionar F1 cuando el control, para que haya establecido el **HelpKeyword** y **HelpNavigator** propiedades: tiene el foco abrirá el archivo de ayuda asociado que <xref:System.Windows.Forms.HelpProvider> componente.  
  
 Actualmente, la propiedad **HelpNamespace** admite archivos de ayuda en los tres formatos siguientes: HTMLHelp 1.x, HTMLHelp 2.0 y HTML. Por lo tanto, puede establecer la propiedad **HelpNamespace** en una dirección http://, como una página web. Si esto sucede, se abrirá el explorador predeterminado en la página web con la cadena especificada en la propiedad **HelpKeyword** utilizada como delimitador. El delimitador se utiliza para saltar a una parte específica de una página HTML.  
  
> [!IMPORTANT]
>  Tenga cuidado de comprobar cualquier información que se envíe desde un cliente antes de utilizarla en su aplicación. Los usuarios malintencionados podrían intentar enviar o inyectar scripts ejecutables, instrucciones SQL u otro código. Antes de mostrar la entrada del usuario, almacénela en una base de datos o trabaje con ella, y compruebe que no contiene información potencialmente insegura. Una forma habitual de comprobación es utilizar una expresión regular para buscar palabras clave como "SCRIPT" cuando se recibe la entrada de un usuario.  
  
 También puede usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente, aunque se haya configurado para mostrar archivos de ayuda para los controles de formularios de Windows. Para más información, consulte [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## <a name="see-also"></a>Vea también  
 [Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [Controlar la ayuda mediante componentes Tooltip](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrar la Ayuda de usuario en Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
