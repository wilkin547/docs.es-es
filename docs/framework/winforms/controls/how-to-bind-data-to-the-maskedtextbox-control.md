---
title: 'Cómo: Enlazar datos al control MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: 0cbb239e24b254c37c453486590185e934adf482
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142178"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="487f1-102">Cómo: Enlazar datos al control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="487f1-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="487f1-103">Puede enlazar datos <xref:System.Windows.Forms.MaskedTextBox> a un control del igual que a cualquier otro control de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="487f1-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="487f1-104">Sin embargo, si el formato de los datos de la base de datos no coincide con el formato esperado por la definición de máscara, deberá volver a formatear los datos.</span><span class="sxs-lookup"><span data-stu-id="487f1-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="487f1-105">El siguiente procedimiento muestra cómo hacerlo <xref:System.Windows.Forms.Binding.Format> <xref:System.Windows.Forms.Binding.Parse> mediante los <xref:System.Windows.Forms.Binding> eventos y de la clase para mostrar campos de base de datos de número de teléfono y extensión de teléfono independientes como un único campo editable.</span><span class="sxs-lookup"><span data-stu-id="487f1-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="487f1-106">El siguiente procedimiento requiere que tenga acceso a una base de datos de SQL Server con la base de datos de ejemplo Northwind instalada.</span><span class="sxs-lookup"><span data-stu-id="487f1-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="487f1-107">Para enlazar datos a un MaskedTextBox control</span><span class="sxs-lookup"><span data-stu-id="487f1-107">To bind data to a MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="487f1-108">Cree un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="487f1-108">Create a new Windows Forms project.</span></span>  
  
2. <span data-ttu-id="487f1-109">Arrastre <xref:System.Windows.Forms.TextBox> dos controles al formulario; nombrarlos `FirstName` `LastName`y .</span><span class="sxs-lookup"><span data-stu-id="487f1-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3. <span data-ttu-id="487f1-110">Arrastre <xref:System.Windows.Forms.MaskedTextBox> un control al formulario; nombre `PhoneMask`.</span><span class="sxs-lookup"><span data-stu-id="487f1-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4. <span data-ttu-id="487f1-111">Establezca <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> la `PhoneMask` propiedad `(000) 000-0000 x9999`de to .</span><span class="sxs-lookup"><span data-stu-id="487f1-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5. <span data-ttu-id="487f1-112">Agregue las siguientes importaciones de espacio de nombres al formulario.</span><span class="sxs-lookup"><span data-stu-id="487f1-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6. <span data-ttu-id="487f1-113">Haga clic con el botón derecho en el formulario y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="487f1-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="487f1-114">Coloque este código en cualquier lugar de la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="487f1-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the
        // initial load.
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7. <span data-ttu-id="487f1-115">Agregue controladores de <xref:System.Windows.Forms.Binding.Format> <xref:System.Windows.Forms.Binding.Parse> eventos para los `PhoneNumber` eventos `Extension` y para <xref:System.Data.DataSet>combinar e separe los campos y del límite.</span><span class="sxs-lookup"><span data-stu-id="487f1-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)
        {  
            ext = "";  
        } else
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8. <span data-ttu-id="487f1-116">Agregue <xref:System.Windows.Forms.Button> dos controles al formulario.</span><span class="sxs-lookup"><span data-stu-id="487f1-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="487f1-117">Nombrarlos `previousButton` `nextButton`y .</span><span class="sxs-lookup"><span data-stu-id="487f1-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="487f1-118">Haga doble clic en <xref:System.Windows.Forms.Control.Click> cada botón para agregar un controlador de eventos y rellene los controladores de eventos como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="487f1-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="487f1-119">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="487f1-119">Run the sample.</span></span> <span data-ttu-id="487f1-120">Edite los datos y utilice los botones **Anterior** y **Siguiente** para <xref:System.Data.DataSet>ver que los datos se conservan correctamente en el archivo .</span><span class="sxs-lookup"><span data-stu-id="487f1-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="487f1-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="487f1-121">Example</span></span>  
 <span data-ttu-id="487f1-122">El ejemplo de código siguiente es la lista de código completa que resulta de completar el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="487f1-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="487f1-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="487f1-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="487f1-124">Cree un proyecto de Visual C o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="487f1-124">Create a Visual C# or Visual Basic project.</span></span>  
  
- <span data-ttu-id="487f1-125">Agregue <xref:System.Windows.Forms.TextBox> los <xref:System.Windows.Forms.MaskedTextBox> controles y al formulario, como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="487f1-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
- <span data-ttu-id="487f1-126">Abra el archivo de código fuente para el formulario predeterminado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="487f1-126">Open the source code file for the project's default form.</span></span>  
  
- <span data-ttu-id="487f1-127">Reemplace el código fuente de este archivo por el código que aparece en la sección anterior "Código".</span><span class="sxs-lookup"><span data-stu-id="487f1-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
- <span data-ttu-id="487f1-128">Realice la compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="487f1-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="487f1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="487f1-129">See also</span></span>

- [<span data-ttu-id="487f1-130">Tutorial: Trabajar con el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="487f1-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
