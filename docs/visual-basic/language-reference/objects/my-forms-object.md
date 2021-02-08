---
description: 'Más información acerca de: My. Forms (objeto)'
title: My.Forms (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 18ef8ee475163ff7eb177dfee590d959a242a88e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774413"
---
# <a name="myforms-object"></a>My.Forms (Objeto)

Proporciona propiedades para obtener acceso a una instancia de cada Windows Forms declarado en el proyecto actual.

## <a name="remarks"></a>Observaciones

El `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad.

Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto utilizando el nombre del formulario, sin calificación. Dado que el nombre de la propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada. Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.

El `My.Forms` objeto expone solo los formularios asociados al proyecto actual. No proporciona acceso a los formularios declarados en los archivos DLL a los que se hace referencia. Para tener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *Nombreformulario*.

Puede utilizar la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de todos los formularios abiertos de la aplicación.

El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.

## <a name="properties"></a>Propiedades

Cada propiedad del `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del formulario.

> [!NOTE]
> Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un formulario es *RootNamespace* _ *espacio de nombres* \_ *formName*. Por ejemplo, considere dos formularios denominados `Form1.` si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1` , tendría acceso a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1` .

El `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio. En el caso de todos los demás formularios, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso a él y lo almacena. Los intentos posteriores de obtener acceso a esa propiedad devuelven esa instancia del formulario.

Puede desechar un formulario asignando `Nothing` a la propiedad de ese formulario. El establecedor de propiedad llama al <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, `Nothing` se asigna al valor almacenado. Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.

Puede comprobar si una propiedad del `My.Forms` objeto almacena una instancia del formulario mediante el `Is` `IsNot` operador o. Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing` .

> [!NOTE]
> Normalmente, el `Is` `IsNot` operador o tiene que leer el valor de la propiedad para realizar la comparación. Sin embargo, si la propiedad almacena actualmente `Nothing` , la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia. Sin embargo, el compilador Visual Basic trata las propiedades del `My.Forms` objeto de forma diferente y permite `Is` que el `IsNot` operador OR Compruebe el estado de la propiedad sin modificar su valor.

## <a name="example"></a>Ejemplo

En este ejemplo se cambia el título del `SidebarMenu` formulario predeterminado.

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

Para que este ejemplo funcione, el proyecto debe tener un formulario denominado `SidebarMenu` .

Este código solo funcionará en un proyecto de aplicación de Windows.

## <a name="requirements"></a>Requisitos

### <a name="availability-by-project-type"></a>Disponibilidad por tipo de proyecto

|Tipo de proyecto|Disponible|
|---|---|
|Aplicación Windows|**Sí**|
|Biblioteca de clases|No|
|Aplicación de consola|No|
|Biblioteca de controles de Windows|No|
|Biblioteca de controles web|No|
|Servicio de Windows|No|
|Sitio web|No|

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [Objetos](index.md)
- [Operador Is](../operators/is-operator.md)
- [Operador IsNot](../operators/isnot-operator.md)
- [Acceso ad los formularios de la aplicación](../../developing-apps/programming/accessing-application-forms.md)
