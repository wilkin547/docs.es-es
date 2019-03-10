---
title: Filtrar Establecer la máscara de entrada
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 53bb8d0e301f83c25ab292b1cb6324dd5f21f100
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702365"
---
# <a name="how-to-set-the-input-mask"></a>Procedimiento Establecer la máscara de entrada
El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar la intervención del usuario. Al establecer la propiedad Mask, puede especificar la entrada del usuario permitido sin escribir ninguna lógica de validación personalizada en la aplicación. Para obtener más información, vea la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox> clase.  
  
## <a name="setting-the-mask-property-manually"></a>Establecer la propiedad Mask manualmente  
 Si está familiarizado con los caracteres que la propiedad Mask admite, puede escribirla manualmente. Para obtener un resumen de los caracteres compatibles con la propiedad de máscara, consulte la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
#### <a name="to-set-the-mask-property-manually"></a>Para establecer la propiedad Mask manualmente  
  
1.  En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  En el **propiedades** ventana, busque la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
3.  Escriba la máscara que desee. Por ejemplo, escriba `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Mediante el cuadro de diálogo de máscara de entrada  
 El cuadro de diálogo de máscara de entrada proporciona algunas máscaras de entrada predefinidos. También puede cambiar las máscaras predefinidas o escribir manualmente su propia máscara.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>Para abrir el cuadro de diálogo de máscara de entrada  
  
1.  En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Haga clic en la etiqueta inteligente para abrir el **MaskedTextBox tareas** panel.  
  
    2.  Haga clic en **establecer máscara**.  
  
     \- o -  
  
    1.  En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.  
  
    2.  Haga clic en el botón de puntos suspensivos en la columna de valor de propiedad.  
  
     El **máscara de entrada** aparece el cuadro de diálogo.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>Para usar el cuadro de diálogo de máscara de entrada  
  
1.  (Opcional) Haga clic en una de las máscaras predefinidas en la lista.  
  
2.  (Opcional) Modifique la máscara predefinida en el **máscara** cuadro.  
  
3.  (Opcional) Escriba una máscara nuevo en el **máscara** cuadro. Es decir, no es necesario utilizar una de las máscaras predefinidas.  
  
    > [!NOTE]
    >  El cuadro de vista previa muestra los caracteres que el usuario ve en el <xref:System.Windows.Forms.MaskedTextBox>. Estos caracteres son una guía para ayudar al usuario escribir los datos correctamente.  
  
4.  Active o desactive el **utilizar ValidatingType** casilla de verificación. El **utilizar ValidatingType** casilla especifica si un tipo de datos se usa para comprobar la entrada de datos por el usuario. Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5.  Haga clic en **Aceptar**.  
  
     La máscara se especifica en el **máscara** propiedad en el **propiedades** ventana.  
  
## <a name="see-also"></a>Vea también
- [Tutorial: Trabajar con el Control MaskedTextBox](walkthrough-working-with-the-maskedtextbox-control.md)
