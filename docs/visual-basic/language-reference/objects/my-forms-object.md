---
title: My. Forms (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9a0b3b9202972122aea4a7147d8d872486418264
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581870"
---
# <a name="myforms-object"></a>My.Forms (Objeto)

Proporciona propiedades para obtener acceso a una instancia de cada Windows Forms declarado en el proyecto actual.

## <a name="remarks"></a>Comentarios

El objeto `My.Forms` proporciona una instancia de cada formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad.

Puede tener acceso a los formularios proporcionados por el objeto `My.Forms` utilizando el nombre del formulario, sin calificación. Dado que el nombre de la propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada. Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.

El objeto `My.Forms` expone solo los formularios asociados al proyecto actual. No proporciona acceso a los formularios declarados en los archivos DLL a los que se hace referencia. Para tener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *Nombreformulario*.

Puede usar la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> para obtener una colección de todos los formularios abiertos de la aplicación.

El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.

## <a name="properties"></a>Propiedades

Cada propiedad del objeto `My.Forms` proporciona acceso a una instancia de un formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del formulario.

> [!NOTE]
> Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un formulario es *RootNamespace*_*namespace* \_*formName*. Por ejemplo, considere dos formularios denominados `Form1.`If uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, tendría acceso a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.

El objeto `My.Forms` proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio. En el caso de todos los demás formularios, el objeto `My.Forms` crea una instancia nueva del formulario cuando se tiene acceso a ella y la almacena. Los intentos posteriores de obtener acceso a esa propiedad devuelven esa instancia del formulario.

Puede desechar un formulario asignando `Nothing` a la propiedad de ese formulario. El establecedor de propiedad llama al método <xref:System.Windows.Forms.Form.Close%2A> del formulario y, a continuación, asigna `Nothing` al valor almacenado. Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una excepción de <xref:System.ArgumentException>.

Puede comprobar si una propiedad del objeto `My.Forms` almacena una instancia del formulario mediante el operador `Is` o `IsNot`. Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing`.

> [!NOTE]
> Normalmente, el operador `Is` o `IsNot` tiene que leer el valor de la propiedad para realizar la comparación. Sin embargo, si la propiedad almacena actualmente `Nothing`, la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia. Sin embargo, el compilador Visual Basic trata las propiedades del objeto `My.Forms` de forma diferente y permite que el operador `Is` o `IsNot` Compruebe el estado de la propiedad sin modificar su valor.

## <a name="example"></a>Ejemplo

En este ejemplo se cambia el título del formulario `SidebarMenu` predeterminado.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Para que este ejemplo funcione, el proyecto debe tener un formulario denominado `SidebarMenu`.

Este código solo funcionará en un proyecto de aplicación de Windows.

## <a name="requirements"></a>Requisitos

### <a name="availability-by-project-type"></a>Disponibilidad por tipo de proyecto

|Tipo de proyecto|Disponible|
|---|---|
|Aplicación Windows|**Sí**|
|Biblioteca de clases|No|
|Aplicación de consola|No|
|Biblioteca de controles de Windows|No|
|Biblioteca de controles Web|No|
|Servicio de Windows|No|
|Sitio web|No|

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [Objects](../../../visual-basic/language-reference/objects/index.md)
- [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Acceso ad los formularios de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
