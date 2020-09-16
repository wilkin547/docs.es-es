---
title: Conservar un objeto en Visual Studio
ms.date: 07/20/2015
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
ms.openlocfilehash: 3febd3f74510d11a7103edbd52bcae8043a5edc0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558607"
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a><span data-ttu-id="0b992-102">Tutorial: Conservar un objeto en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b992-102">Walkthrough: Persisting an Object in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="0b992-103">Aunque puede establecer las propiedades de un objeto en los valores predeterminados en el tiempo de diseño, cualquier valor que se establezca en tiempo de ejecución se pierde cuando se destruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="0b992-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="0b992-104">Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="0b992-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b992-105">En Visual Basic, para almacenar datos simples, como un nombre o número, puede utilizar el objeto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="0b992-105">In Visual Basic, to store simple data, such as a name or number, you can use the `My.Settings` object.</span></span> <span data-ttu-id="0b992-106">Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="0b992-106">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
 <span data-ttu-id="0b992-107">En este tutorial, creará un objeto `Loan` sencillo y conservará sus datos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0b992-107">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="0b992-108">Después, recuperará los datos del archivo cuando vuelva a crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="0b992-108">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0b992-109">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="0b992-109">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="0b992-110">Si una aplicación debe crear un archivo, debe `Create` permiso para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0b992-110">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="0b992-111">Los permisos se establecen mediante el uso de las listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="0b992-111">Permissions are set by using access control lists.</span></span> <span data-ttu-id="0b992-112">Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor.</span><span class="sxs-lookup"><span data-stu-id="0b992-112">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="0b992-113">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta).</span><span class="sxs-lookup"><span data-stu-id="0b992-113">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="0b992-114">Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="0b992-114">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0b992-115">En este ejemplo se almacenan datos en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="0b992-115">This example stores data in a binary.</span></span> <span data-ttu-id="0b992-116">Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="0b992-116">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b992-117">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="0b992-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0b992-118">Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0b992-118">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0b992-119">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="0b992-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="0b992-120">Crear el objeto Loan</span><span class="sxs-lookup"><span data-stu-id="0b992-120">Creating the Loan Object</span></span>  
 <span data-ttu-id="0b992-121">El primer paso consiste en crear una clase `Loan` y una aplicación de prueba que use la clase.</span><span class="sxs-lookup"><span data-stu-id="0b992-121">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="0b992-122">Para crear la clase Loan</span><span class="sxs-lookup"><span data-stu-id="0b992-122">To create the Loan class</span></span>  
  
1. <span data-ttu-id="0b992-123">Cree un nuevo proyecto de bibliotecas de clases y denomínelo "LoanClass".</span><span class="sxs-lookup"><span data-stu-id="0b992-123">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="0b992-124">Para más información, vea [Crear soluciones y proyectos](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="0b992-124">For more information, see [Creating Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2. <span data-ttu-id="0b992-125">En el **Explorador de soluciones**, abra el menú contextual del archivo Class1 y pulse **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="0b992-125">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="0b992-126">Cambie el nombre del archivo a `Loan` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0b992-126">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="0b992-127">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `Loan`.</span><span class="sxs-lookup"><span data-stu-id="0b992-127">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3. <span data-ttu-id="0b992-128">Agregue los siguientes miembros públicos a la clase:</span><span class="sxs-lookup"><span data-stu-id="0b992-128">Add the following public members to the class:</span></span>  
  
    ```vb  
    Public Class Loan  
        Implements System.ComponentModel.INotifyPropertyChanged  
  
        Public Property LoanAmount As Double  
        Public Property InterestRate As Double  
        Public Property Term As Integer  
  
        Private p_Customer As String  
        Public Property Customer As String  
            Get  
                Return p_Customer  
            End Get  
            Set(ByVal value As String)  
                p_Customer = value  
                RaiseEvent PropertyChanged(Me,  
                  New System.ComponentModel.PropertyChangedEventArgs("Customer"))  
            End Set  
        End Property  
  
        Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
          Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
  
        Public Sub New(ByVal loanAmount As Double,  
                       ByVal interestRate As Double,  
                       ByVal term As Integer,  
                       ByVal customer As String)  
  
            Me.LoanAmount = loanAmount  
            Me.InterestRate = interestRate  
            Me.Term = term  
            p_Customer = customer  
        End Sub  
    End Class  
    ```  
  
 <span data-ttu-id="0b992-129">También tendrá que crear una aplicación sencilla que use la clase `Loan`.</span><span class="sxs-lookup"><span data-stu-id="0b992-129">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="0b992-130">Para crear una aplicación de prueba</span><span class="sxs-lookup"><span data-stu-id="0b992-130">To create a test application</span></span>  
  
1. <span data-ttu-id="0b992-131">Para agregar un proyecto de Aplicación de Windows Forms a su solución, en el menú **Archivo**, seleccione **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0b992-131">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**,**New Project**.</span></span>  
  
2. <span data-ttu-id="0b992-132">En el cuadro de diálogo **Agregar nuevo proyecto**, pulse **Aplicación de Windows Forms** y escriba `LoanApp` como el nombre del proyecto y, después, haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b992-132">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="0b992-133">En el **Explorador de soluciones**, elija el proyecto de LoanApp.</span><span class="sxs-lookup"><span data-stu-id="0b992-133">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4. <span data-ttu-id="0b992-134">En el menú **Proyecto**, seleccione **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="0b992-134">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="0b992-135">En el menú **proyecto** , elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="0b992-135">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6. <span data-ttu-id="0b992-136">En el cuadro de diálogo **Agregar referencia**, pulse la pestaña **Proyectos** y, después, elija el proyecto de LoanClass.</span><span class="sxs-lookup"><span data-stu-id="0b992-136">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7. <span data-ttu-id="0b992-137">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0b992-137">Click **OK** to close the dialog box.</span></span>  
  
8. <span data-ttu-id="0b992-138">En el diseñador, agregue cuatro controles <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="0b992-138">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="0b992-139">En el Editor de códigos, agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="0b992-139">In the Code Editor, add the following code:</span></span>  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. <span data-ttu-id="0b992-140">Agregue un controlador de eventos para el evento `PropertyChanged` al formulario con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b992-140">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 <span data-ttu-id="0b992-141">En este punto, podrá compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b992-141">At this point, you can build and run the application.</span></span> <span data-ttu-id="0b992-142">Tenga en cuenta que los valores predeterminados de la clase `Loan` aparecen en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="0b992-142">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="0b992-143">Intente cambiar el valor de la tasa de interés de 7,5 a 7,1 y, después, cierre la aplicación y ejecútela de nuevo; el valor vuelve a ser el valor predeterminado de 7,5.</span><span class="sxs-lookup"><span data-stu-id="0b992-143">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="0b992-144">En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b992-144">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="0b992-145">En lugar de hacer que el usuario actualice la tasa de interés cada vez que se ejecuta la aplicación, es mejor conservar la tasa de interés más reciente entre instancias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b992-145">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="0b992-146">En el paso siguiente, hará esto agregando la serialización a la clase Loan.</span><span class="sxs-lookup"><span data-stu-id="0b992-146">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="0b992-147">Usar la serialización para conservar el objeto</span><span class="sxs-lookup"><span data-stu-id="0b992-147">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="0b992-148">Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="0b992-148">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="0b992-149">Para marcar una clase como serializable</span><span class="sxs-lookup"><span data-stu-id="0b992-149">To mark a class as serializable</span></span>  
  
- <span data-ttu-id="0b992-150">Cambie la declaración de clase para la clase Loan de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b992-150">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 <span data-ttu-id="0b992-151">El atributo `Serializable` indica al compilador que todo el contenido de la clase puede conservarse en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0b992-151">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="0b992-152">Como el evento `PropertyChanged` está controlado por un objeto de Windows Forms, no puede serializarse.</span><span class="sxs-lookup"><span data-stu-id="0b992-152">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="0b992-153">El atributo `NonSerialized` puede usarse para marcar miembros de clase que no deben conservarse.</span><span class="sxs-lookup"><span data-stu-id="0b992-153">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="0b992-154">Para evitar que un miembro se serialice</span><span class="sxs-lookup"><span data-stu-id="0b992-154">To prevent a member from being serialized</span></span>  
  
- <span data-ttu-id="0b992-155">Cambie la declaración del evento `PropertyChanged` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b992-155">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 <span data-ttu-id="0b992-156">El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp.</span><span class="sxs-lookup"><span data-stu-id="0b992-156">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="0b992-157">Para serializar la clase y escribirla en un archivo, usará los espacios de nombres <xref:System.IO> y <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="0b992-157">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="0b992-158">Para evitar escribir los nombres completos, puede agregar referencias a las bibliotecas de clase necesarias.</span><span class="sxs-lookup"><span data-stu-id="0b992-158">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="0b992-159">Para agregar referencias a los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="0b992-159">To add references to namespaces</span></span>  
  
- <span data-ttu-id="0b992-160">Agregue las instrucciones siguientes en la parte superior de la clase `Form1`:</span><span class="sxs-lookup"><span data-stu-id="0b992-160">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     <span data-ttu-id="0b992-161">En este caso, está usando un formateador binario para guardar el objeto en un formato binario.</span><span class="sxs-lookup"><span data-stu-id="0b992-161">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="0b992-162">El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea.</span><span class="sxs-lookup"><span data-stu-id="0b992-162">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="0b992-163">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="0b992-163">To deserialize an object</span></span>  
  
1. <span data-ttu-id="0b992-164">Agregue una constante a la clase para el nombre de archivo de los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="0b992-164">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2. <span data-ttu-id="0b992-165">Modifique el código en el procedimiento de evento `Form1_Load` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b992-165">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        If File.Exists(FileName) Then  
            Dim TestFileStream As Stream = File.OpenRead(FileName)  
            Dim deserializer As New BinaryFormatter  
            TestLoan = CType(deserializer.Deserialize(TestFileStream), LoanClass.Loan)  
            TestFileStream.Close()  
        End If  
  
        AddHandler TestLoan.PropertyChanged, AddressOf Me.CustomerPropertyChanged  
  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
     <span data-ttu-id="0b992-166">Tenga en cuenta que primero debe comprobar que existe el archivo.</span><span class="sxs-lookup"><span data-stu-id="0b992-166">Note that you first must check that the file exists.</span></span> <span data-ttu-id="0b992-167">Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo.</span><span class="sxs-lookup"><span data-stu-id="0b992-167">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="0b992-168">También necesita convertir del tipo de secuencia al tipo de objeto Loan.</span><span class="sxs-lookup"><span data-stu-id="0b992-168">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="0b992-169">Después, debe agregar código para guardar los datos que se han escrito en los cuadros de texto en la clase `Loan` y, luego, debe serializar la clase en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0b992-169">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="0b992-170">Para guardar los datos y serializar la clase</span><span class="sxs-lookup"><span data-stu-id="0b992-170">To save the data and serialize the class</span></span>  
  
- <span data-ttu-id="0b992-171">Agregue el código siguiente al procedimiento de eventos `Form1_FormClosing`:</span><span class="sxs-lookup"><span data-stu-id="0b992-171">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
    ```vb  
    Private Sub Form1_FormClosing() Handles MyBase.FormClosing  
        TestLoan.LoanAmount = CDbl(TextBox1.Text)  
        TestLoan.InterestRate = CDbl(TextBox2.Text)  
        TestLoan.Term = CInt(TextBox3.Text)  
        TestLoan.Customer = TextBox4.Text  
  
        Dim TestFileStream As Stream = File.Create(FileName)  
        Dim serializer As New BinaryFormatter  
        serializer.Serialize(TestFileStream, TestLoan)  
        TestFileStream.Close()  
    End Sub  
    ```  
  
 <span data-ttu-id="0b992-172">En este punto, podrá compilar y ejecutar la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0b992-172">At this point, you can again build and run the application.</span></span> <span data-ttu-id="0b992-173">Inicialmente, los valores predeterminados aparecen en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="0b992-173">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="0b992-174">Pruebe a cambiar los valores y escriba un nombre en el cuarto cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="0b992-174">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="0b992-175">Cierre la aplicación y, después, ejecútela de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0b992-175">Close the application and then run it again.</span></span> <span data-ttu-id="0b992-176">Tenga en cuenta que los valores nuevos aparecen ahora en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="0b992-176">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b992-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b992-177">See also</span></span>

- [<span data-ttu-id="0b992-178">Serialización (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b992-178">Serialization (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="0b992-179">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b992-179">Visual Basic Programming Guide</span></span>](../../index.md)
