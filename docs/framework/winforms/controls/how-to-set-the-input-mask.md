---
title: Procedimiento para establecer la máscara de entrada
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949147"
---
# <a name="how-to-set-the-input-mask"></a>Procedimiento para establecer la máscara de entrada
El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar la entrada del usuario. Al establecer la propiedad Mask, puede especificar la entrada de usuario permitida sin escribir ninguna lógica de validación personalizada en la aplicación. Para obtener más información, vea la sección Comentarios de <xref:System.Windows.Forms.MaskedTextBox> la clase.  
  
## <a name="setting-the-mask-property-manually"></a>Establecimiento manual de la propiedad Mask  
 Si está familiarizado con los caracteres que admite la propiedad Mask, puede especificarlos manualmente. Para obtener un resumen de los caracteres que admite la propiedad Mask, vea la sección Comentarios de <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> la propiedad.  
  
### <a name="to-set-the-mask-property-manually"></a>Para establecer la propiedad Mask manualmente  
  
1. En la vista **diseño** , seleccione <xref:System.Windows.Forms.MaskedTextBox>un.  
  
2. En la ventana **propiedades** , busque la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
3. Escriba la máscara que desee. Por ejemplo, escriba `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Usar el cuadro de diálogo máscara de entrada  
 El cuadro de diálogo máscara de entrada proporciona algunas máscaras de entrada predefinidas. También puede cambiar las máscaras predefinidas o escribir su propia máscara manualmente.  
  
### <a name="to-open-the-input-mask-dialog-box"></a>Para abrir el cuadro de diálogo máscara de entrada  
  
1. En la vista **diseño** , seleccione <xref:System.Windows.Forms.MaskedTextBox>un.  
  
    1. Haga clic en la etiqueta inteligente para abrir el panel de **tareas de MaskedTextBox** .  
  
    2. Haga clic en **establecer máscara**.  
  
     \- o -  
  
    1. En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
    2. Haga clic en el botón de puntos suspensivos en la columna valor de propiedad.  
  
     Aparece el cuadro de diálogo **máscara de entrada** .  
  
### <a name="to-use-the-input-mask-dialog-box"></a>Para usar el cuadro de diálogo máscara de entrada  
  
1. Opta Haga clic en una de las máscaras predefinidas de la lista.  
  
2. Opta Edite la máscara predefinida en el cuadro **máscara** .  
  
3. Opta Escriba una nueva máscara en el cuadro **máscara** . Es decir, no tiene que utilizar una de las máscaras predefinidas.  
  
    > [!NOTE]
    > El cuadro vista previa muestra los caracteres que el usuario ve en <xref:System.Windows.Forms.MaskedTextBox>el. Estos caracteres son una guía para ayudar al usuario a escribir los datos correctamente.  
  
4. Active o desactive la casilla **usar ValidatingType** . La casilla **usar ValidatingType** especifica si se utiliza un tipo de datos para comprobar la entrada de datos por parte del usuario. Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5. Haga clic en **OK**.  
  
     La máscara se especifica en la propiedad **Mask** de la ventana **propiedades** .  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Trabajar con el control MaskedTextBox](walkthrough-working-with-the-maskedtextbox-control.md)
