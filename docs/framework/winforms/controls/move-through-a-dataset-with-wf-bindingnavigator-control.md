---
title: Desplazarse por un conjunto de DataSet con el control BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 73a102da74a3a2a00b5042331cffcaf3d858ea5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742152"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="eff4c-102">Cómo: Desplazarse por un conjunto de datos con el control BindingNavigator de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eff4c-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="eff4c-103">Al crear aplicaciones controladas por datos, a menudo necesitará mostrar colecciones de datos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="eff4c-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="eff4c-104">El control <xref:System.Windows.Forms.BindingNavigator>, junto con el componente <xref:System.Windows.Forms.BindingSource>, proporciona una solución cómoda y extensible para desplazarse por una colección y mostrar sus elementos secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="eff4c-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eff4c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eff4c-105">Example</span></span>  
 <span data-ttu-id="eff4c-106">En el ejemplo de código siguiente, se muestra cómo usar el control <xref:System.Windows.Forms.BindingNavigator> para desplazarse por los datos.</span><span class="sxs-lookup"><span data-stu-id="eff4c-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="eff4c-107">El conjunto está contenido en un <xref:System.Data.DataView>, que enlaza a un control <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="eff4c-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eff4c-108">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eff4c-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="eff4c-109">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="eff4c-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="eff4c-110">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="eff4c-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eff4c-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="eff4c-111">Compiling the Code</span></span>  
 <span data-ttu-id="eff4c-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="eff4c-112">This example requires:</span></span>  
  
- <span data-ttu-id="eff4c-113">Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="eff4c-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff4c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eff4c-114">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="eff4c-115">BindingNavigator (control)</span><span class="sxs-lookup"><span data-stu-id="eff4c-115">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="eff4c-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="eff4c-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="eff4c-117">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="eff4c-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
