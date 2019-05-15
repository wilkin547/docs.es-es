---
title: Procedimiento Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: 16f23fac53cee5f6c007df6046e73cb7d9e1fbca
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589202"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="4f4a1-102">Procedimiento para crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f4a1-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="4f4a1-103">En el ejemplo de código siguiente se crea un formulario Maestro y detalles mediante dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos componentes <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="4f4a1-104">El origen de datos es un <xref:System.Data.DataSet> que contiene las tablas `Customers` y `Orders` de la base de datos de ejemplo de SQL Server Northwind, junto con una <xref:System.Data.DataRelation> que relaciona las dos mediante la columna `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="4f4a1-105">Un <xref:System.Windows.Forms.BindingSource> se enlaza a la tabla primaria `Customers` del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="4f4a1-106">Estos datos se muestran en el control maestro <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4f4a1-107">El otro <xref:System.Windows.Forms.BindingSource> se enlaza al primer conector de datos.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="4f4a1-108">La propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> del segundo <xref:System.Windows.Forms.BindingSource> se establece en el nombre <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="4f4a1-109">Esto hace que el control de detalles asociados <xref:System.Windows.Forms.DataGridView> muestre las filas de la tabla secundaria `Orders` que corresponden a la fila actual del control maestro <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="4f4a1-110">Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Creación de un formulario principal-detalle mediante dos Windows Forms DataGridView controles](creating-a-master-detail-form-using-two-datagridviews.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a1-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4a1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f4a1-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f4a1-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4f4a1-112">Compiling the Code</span></span>  
 <span data-ttu-id="4f4a1-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4f4a1-113">This example requires:</span></span>  
  
 <span data-ttu-id="4f4a1-114">Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4f4a1-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f4a1-115">.NET Framework Security</span></span>  
 <span data-ttu-id="4f4a1-116">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-116">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="4f4a1-117">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4f4a1-117">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="4f4a1-118">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a1-118">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4a1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f4a1-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="4f4a1-120">Tutorial: Creación de un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f4a1-120">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="4f4a1-121">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f4a1-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4f4a1-122">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="4f4a1-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
