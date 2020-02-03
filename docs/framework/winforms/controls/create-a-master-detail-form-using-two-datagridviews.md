---
title: Crear un formulario principal-detalle mediante dos controles DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d317f4e592790c9b48b539b1601814569e14529f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737334"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="885fd-102">Cómo: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="885fd-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="885fd-103">En el ejemplo de código siguiente se crea un formulario Maestro y detalles mediante dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos componentes <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="885fd-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="885fd-104">El origen de datos es un <xref:System.Data.DataSet> que contiene las tablas `Customers` y `Orders` de la base de datos de ejemplo de SQL Server Northwind, junto con una <xref:System.Data.DataRelation> que relaciona las dos mediante la columna `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="885fd-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="885fd-105">Un <xref:System.Windows.Forms.BindingSource> se enlaza a la tabla primaria `Customers` del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="885fd-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="885fd-106">Estos datos se muestran en el control maestro <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="885fd-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="885fd-107">El otro <xref:System.Windows.Forms.BindingSource> se enlaza al primer conector de datos.</span><span class="sxs-lookup"><span data-stu-id="885fd-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="885fd-108">La propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> del segundo <xref:System.Windows.Forms.BindingSource> se establece en el nombre <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="885fd-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="885fd-109">Esto hace que el control de detalles asociados <xref:System.Windows.Forms.DataGridView> muestre las filas de la tabla secundaria `Orders` que corresponden a la fila actual del control maestro <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="885fd-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="885fd-110">Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: crear un formulario principal-detalle mediante dos controles DataGridView Windows Forms](creating-a-master-detail-form-using-two-datagridviews.md).</span><span class="sxs-lookup"><span data-stu-id="885fd-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="885fd-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="885fd-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="885fd-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="885fd-112">Compiling the Code</span></span>  
 <span data-ttu-id="885fd-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="885fd-113">This example requires:</span></span>  
  
 <span data-ttu-id="885fd-114">Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.</span><span class="sxs-lookup"><span data-stu-id="885fd-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="885fd-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="885fd-115">.NET Framework Security</span></span>  
 <span data-ttu-id="885fd-116">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="885fd-116">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="885fd-117">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="885fd-117">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="885fd-118">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="885fd-118">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885fd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="885fd-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="885fd-120">Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="885fd-120">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="885fd-121">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="885fd-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="885fd-122">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="885fd-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
