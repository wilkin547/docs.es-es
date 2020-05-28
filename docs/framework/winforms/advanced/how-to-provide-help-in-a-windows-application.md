---
title: Procedimiento para proporcionar ayuda en una aplicación Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 405de333ce936a864047e827e60f56a930059e26
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143633"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Procedimiento para proporcionar ayuda en una aplicación Windows

Puede usar el <xref:System.Windows.Forms.HelpProvider> componente para adjuntar los temas de ayuda de un archivo de ayuda a controles específicos en Windows Forms. El archivo de ayuda puede ser HTML, HTMLHelp 1.x o superior.

## <a name="provide-help"></a>Proporcionar ayuda

1. En Visual Studio, en el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.HelpProvider> componente al formulario.

     El componente estará en la bandeja, en la parte inferior del Diseñador de Windows Forms.

2. En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad en el archivo de ayuda. chm,. col o. htm.

3. Seleccione otro control que tenga en el formulario y, en la ventana **propiedades** , establezca la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> propiedad.

     Esta es la cadena que se pasa a través del <xref:System.Windows.Forms.HelpProvider> componente al archivo de ayuda para convocar el tema de ayuda adecuado.

4. En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> propiedad en un valor de la <xref:System.Windows.Forms.HelpNavigator> enumeración.

     Esto determina la forma en la que la propiedad **HelpKeyword** pasa al sistema de ayuda. La siguiente tabla muestra los valores posibles y sus descripciones.

    |Nombre de miembro|Description|
    |-----------------|-----------------|
    |AssociateIndex|Especifica que el índice de un tema determinado se realiza en la dirección URL especificada.|
    |Buscar|Especifica que se muestre la página de búsqueda de una dirección URL especificada.|
    |Índice|Especifica que se muestre el índice de una dirección URL especificada.|
    |KeywordIndex|Especifica una palabra clave que buscar y la acción que se realizará en la dirección URL especificada.|
    |TableOfContents|Especifica que se muestra la tabla de contenidos del archivo de ayuda HTML 1.0.|
    |Tema|Especifica que se muestra el tema al que hace referencia la dirección URL especificada.|

 En tiempo de ejecución, al presionar F1 cuando el control (para el que ha establecido las propiedades **HelpKeyword** y **HelpNavigator** ) tiene el foco, se abrirá el archivo de ayuda asociado a ese <xref:System.Windows.Forms.HelpProvider> componente.

 Actualmente, la propiedad **HelpNamespace** admite archivos de ayuda en los tres formatos siguientes: HTMLHelp 1.x, HTMLHelp 2.0 y HTML. Por lo tanto, puede establecer la propiedad **HelpNamespace** en una `http://` dirección, como una página web. Si esto sucede, se abrirá el explorador predeterminado en la página web con la cadena especificada en la propiedad **HelpKeyword** utilizada como delimitador. El delimitador se utiliza para saltar a una parte específica de una página HTML.

> [!IMPORTANT]
> Tenga cuidado de comprobar cualquier información que se envíe desde un cliente antes de utilizarla en su aplicación. Los usuarios malintencionados podrían intentar enviar o inyectar scripts ejecutables, instrucciones SQL u otro código. Antes de mostrar la entrada del usuario, almacénela en una base de datos o trabaje con ella, y compruebe que no contiene información potencialmente insegura. Una forma habitual de comprobación es utilizar una expresión regular para buscar palabras clave como "SCRIPT" cuando se recibe la entrada de un usuario.

También puede usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar la ayuda emergente, incluso si está configurado para mostrar los archivos de ayuda de los controles en el Windows Forms. Para más información, consulte [Cómo: Mostrar ayuda emergente](how-to-display-pop-up-help.md).

## <a name="see-also"></a>Vea también

- [Procedimiento para mostrar ayuda emergente](how-to-display-pop-up-help.md)
- [Controlar la ayuda mediante información sobre herramientas](control-help-using-tooltips.md)
- [Integrar la Ayuda de usuario en formularios Windows Forms](integrating-user-help-in-windows-forms.md)
- [Windows Forms](../index.md)
