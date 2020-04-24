---
title: Validación de entrada de usuario
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646298"
---
# <a name="user-input-validation-in-windows-forms"></a>Validación de los datos proporcionados por el usuario en formularios Windows Forms
Cuando los usuarios escriben datos en la aplicación, es posible que desee comprobar que los datos son válidos antes de que la aplicación los use. Puede requerir que ciertos campos de texto no tengan longitud cero, que un campo tenga formato como un número de teléfono u otro tipo de datos bien formados, o que una cadena no contenga caracteres no seguros que puedan utilizarse para poner en peligro la seguridad de una base de datos. Windows Forms proporciona varias maneras de validar la entrada en la aplicación.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validación con el control MaskedTextBox  
 Si necesita requerir que los usuarios introduzcan datos en un formato bien definido, como un número de teléfono <xref:System.Windows.Forms.MaskedTextBox> o un número de pieza, puede lograrlo rápidamente y con un código mínimo mediante el control. Una *máscara* es una cadena formada por caracteres de un lenguaje de enmascaramiento que especifica qué caracteres se pueden introducir en cualquier posición determinada del cuadro de texto. El control muestra un conjunto de solicitudes al usuario. Si el usuario escribe una entrada incorrecta, por ejemplo, el usuario escribe una letra cuando se requiere un dígito, el control rechazará automáticamente la entrada.  
  
 El lenguaje de enmascaramiento <xref:System.Windows.Forms.MaskedTextBox> que se utiliza es muy flexible. Le permite especificar caracteres necesarios, caracteres opcionales, caracteres literales, como guiones y paréntesis, caracteres de moneda y separadores de fecha. El control también funciona bien cuando se enlaza a un origen de datos. El <xref:System.Windows.Forms.Binding.Format> evento en un enlace de datos se puede utilizar para <xref:System.Windows.Forms.Binding.Parse> reformatear los datos entrantes para cumplir con la máscara, y el evento se puede utilizar para reformatear los datos salientes para cumplir con las especificaciones del campo de datos.  
  
 Para obtener más información, vea [MaskedTextBox Control](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Validación controlada por eventos  
 Si desea un control completo mediante programación sobre la validación o necesita realizar comprobaciones de validación complejas, debe usar los eventos de validación integrados en la mayoría de los controles de formularios Windows Forms. Cada control que acepta la entrada <xref:System.Windows.Forms.Control.Validating> del usuario de forma libre tiene un evento que se producirá siempre que el control requiera la validación de datos. En <xref:System.Windows.Forms.Control.Validating> el método de control de eventos, puede validar la entrada del usuario de varias maneras. Por ejemplo, si tiene un cuadro de texto que debe contener un código postal, puede realizar la validación de las siguientes maneras:  
  
- Si el código postal debe pertenecer a un grupo específico de códigos postales, puede realizar una comparación de cadenas en la entrada para validar los datos introducidos por el usuario. Por ejemplo, si el código postal debe estar en el conjunto de valores 10001, 10002, 10003, puede usar una comparación de cadenas para validar los datos.  
  
- Si el código postal debe estar en un formulario específico, puede utilizar expresiones regulares para validar los datos introducidos por el usuario. Por ejemplo, para `#####` validar `#####-####`el formulario o `^(\d{5})(-\d{4})?$`, puede utilizar la expresión regular . Para validar `A#A #A#`el formulario, puede `[A-Z]\d[A-Z] \d[A-Z]\d`utilizar la expresión regular . Para obtener más información acerca de las expresiones regulares, vea [Expresiones regulares](../../standard/base-types/regular-expressions.md) de .NET Framework y Ejemplos de [expresiones regulares](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md).  
  
- Si el código postal debe ser un código postal válido de los Estados Unidos, puede llamar a un servicio web de código postal para validar los datos introducidos por el usuario.  
  
 El <xref:System.Windows.Forms.Control.Validating> evento se proporciona <xref:System.ComponentModel.CancelEventArgs>un objeto de tipo . Si determina que los datos del control no son <xref:System.Windows.Forms.Control.Validating> válidos, puede <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> cancelar `true`el evento estableciendo la propiedad de este objeto en . Si no establece <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> la propiedad, Windows Forms asumirá que la validación se realizó correctamente para ese control y generará el <xref:System.Windows.Forms.Control.Validated> evento.  
  
 Para obtener un ejemplo de código <xref:System.Windows.Controls.TextBox>que <xref:System.Windows.Forms.Control.Validating>valida una dirección de correo electrónico en un archivo , vea .  
  
### <a name="data-binding-and-event-driven-validation"></a>Enlace de datos y validación controlada por eventos  
 La validación es muy útil cuando se han enlazado los controles a un origen de datos, como una tabla de base de datos. Mediante la validación, puede asegurarse de que los datos del control satisfacen el formato requerido por el origen de datos y de que no contienen caracteres especiales, como comillas y barras diagonales inversas que podrían no ser seguros.  
  
 Cuando se usa el enlace de datos, los datos del control <xref:System.Windows.Forms.Control.Validating> se sincronizan con el origen de datos durante la ejecución del evento. Si cancela <xref:System.Windows.Forms.Control.Validating> el evento, los datos no se sincronizarán con el origen de datos.  
  
> [!IMPORTANT]
> Si tiene una validación personalizada <xref:System.Windows.Forms.Control.Validating> que tiene lugar después del evento, no afectará al enlace de datos. Por ejemplo, si tiene <xref:System.Windows.Forms.Control.Validated> código en un evento que intenta cancelar el enlace de datos, el enlace de datos seguirá produciéndose. En este caso, para <xref:System.Windows.Forms.Control.Validated> realizar la validación en el evento, cambie la propiedad Modo de actualización del **origen** de datos del control **(en (Enlaces de datos)**\\ **(avanzado)** de **OnValidation** a **Never**y agregue *Control*`.DataBindings["`*\<YOURFIELD>* `"].WriteValue()` al código de validación.  
  
### <a name="implicit-and-explicit-validation"></a>Validación implícita y explícita  
 Entonces, ¿cuándo se validan los datos de un control? Esto depende de ti, el desarrollador. Puede usar la validación implícita o explícita, en función de las necesidades de la aplicación.  
  
#### <a name="implicit-validation"></a>Validación implícita  
 El enfoque de validación implícita valida los datos a medida que el usuario los escribe. Puede validar los datos a medida que los datos se introducen en un control leyendo las teclas a medida que se presionan, o más comúnmente cada vez que el usuario quita el foco de entrada de un control y se mueve al siguiente. Este enfoque es útil cuando desea proporcionar al usuario comentarios inmediatos sobre los datos mientras están trabajando.  
  
 Si desea usar la validación implícita para un control, debe establecer la propiedad de <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> ese control en <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> o <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>. Si cancela <xref:System.Windows.Forms.Control.Validating> el evento, el comportamiento del control se determinará <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>por el valor que asignó a . Si ha <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>asignado , la cancelación del evento hará que el <xref:System.Windows.Forms.Control.Validated> evento no se produzca. El foco de entrada permanecerá en el control actual hasta que el usuario cambie los datos a una entrada válida. Si ha <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>asignado <xref:System.Windows.Forms.Control.Validated> , el evento no se producirá al cancelar el evento, pero el foco cambiará al siguiente control.  
  
 La <xref:System.Windows.Forms.AutoValidate.Disable> asignación a la propiedad impide la <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> validación implícita por completo. Para validar los controles, tendrá que usar la validación explícita.  
  
#### <a name="explicit-validation"></a>Validación explícita  
 El enfoque de validación explícita valida los datos a la vez. Puede validar los datos en respuesta a una acción del usuario, como hacer clic en un botón Guardar o en un vínculo Siguiente. Cuando se produce la acción del usuario, puede desencadenar la validación explícita de una de las siguientes maneras:  
  
- Llame <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar el último control que ha perdido el foco.  
  
- Llame <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos los controles secundarios en un control de formulario o contenedor.  
  
- Llame a un método personalizado para validar los datos de los controles manualmente.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Comportamiento de validación implícita predeterminado para controles de formularios Windows Forms  
 Diferentes controles de formularios Windows <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Forms tienen valores predeterminados diferentes para su propiedad. En la tabla siguiente se muestran los controles más comunes y sus valores predeterminados.  
  
|Control|Comportamiento de validación predeterminado|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Cierre del formulario y validación de reemplazo  
 Cuando un control mantiene el foco porque los datos que contiene no son válidos, es imposible cerrar el formulario primario de una de las maneras habituales:  
  
- Haciendo clic en el botón **Cerrar.**  
  
- Seleccionando **Cerrar** en el menú **Sistema.**  
  
- Llamando al <xref:System.Windows.Forms.Form.Close%2A> método mediante programación.  
  
 Sin embargo, en algunos casos, es posible que desee permitir que el usuario cierre el formulario independientemente de si los valores de los controles son válidos. Puede invalidar la validación y cerrar un formulario que todavía contiene <xref:System.Windows.Forms.Form.FormClosing> datos no válidos mediante la creación de un controlador para el evento del formulario. En caso de <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> que, `false`establezca la propiedad en . Esto obliga a cerrar la forma. Para obtener más información y un ejemplo, vea <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Si fuerza el formulario a cerrarse de esta manera, se perderán los datos de los controles del formulario que aún no se hayan guardado. Además, los formularios modales no validan el contenido de los controles cuando se cierran. Todavía puede usar la validación de control para bloquear el foco a un control, pero no tiene que preocuparse por el comportamiento asociado con el cierre del formulario.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [Control MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md)
- [Ejemplos de expresiones regulares](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)
