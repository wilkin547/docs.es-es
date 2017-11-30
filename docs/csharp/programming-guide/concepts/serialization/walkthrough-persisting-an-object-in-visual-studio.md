---
title: 'Tutorial: Conservar un objeto en Visual Studio (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: get-started-article
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: efdf4694c1a1b6df2e9531a2bb4c813b536a330e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a><span data-ttu-id="e9f22-102">Tutorial: Conservar un objeto en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="e9f22-102">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>
<span data-ttu-id="e9f22-103">Aunque puede establecer las propiedades de un objeto en los valores predeterminados en el tiempo de diseño, cualquier valor que se establezca en tiempo de ejecución se pierde cuando se destruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-103">Although you can set an object's properties to default values at design time, any values entered at run time are lost when the object is destroyed.</span></span> <span data-ttu-id="e9f22-104">Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>  
  
 <span data-ttu-id="e9f22-105">En este tutorial, creará un objeto `Loan` sencillo y conservará sus datos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-105">In this walkthrough, you will create a simple `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="e9f22-106">Después, recuperará los datos del archivo cuando vuelva a crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-106">You will then retrieve the data from the file when you re-create the object.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9f22-107">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="e9f22-107">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="e9f22-108">Si una aplicación debe crear un archivo, debe `Create` permiso para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="e9f22-108">If an application must create a file, that application must `Create` permission for the folder.</span></span> <span data-ttu-id="e9f22-109">Los permisos se establecen mediante el uso de las listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="e9f22-109">Permissions are set by using access control lists.</span></span> <span data-ttu-id="e9f22-110">Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor.</span><span class="sxs-lookup"><span data-stu-id="e9f22-110">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="e9f22-111">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta).</span><span class="sxs-lookup"><span data-stu-id="e9f22-111">Where possible, it is more secure to create the file during deployment, and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="e9f22-112">Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="e9f22-112">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9f22-113">En este ejemplo se almacenan datos en un archivo de formato binario.</span><span class="sxs-lookup"><span data-stu-id="e9f22-113">This example stores data in a binary format file.</span></span> <span data-ttu-id="e9f22-114">Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="e9f22-114">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9f22-115">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="e9f22-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e9f22-116">Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="e9f22-116">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e9f22-117">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="e9f22-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-loan-object"></a><span data-ttu-id="e9f22-118">Crear el objeto Loan</span><span class="sxs-lookup"><span data-stu-id="e9f22-118">Creating the Loan Object</span></span>  
 <span data-ttu-id="e9f22-119">El primer paso consiste en crear una clase `Loan` y una aplicación de prueba que use la clase.</span><span class="sxs-lookup"><span data-stu-id="e9f22-119">The first step is to create a `Loan` class and a test application that uses the class.</span></span>  
  
### <a name="to-create-the-loan-class"></a><span data-ttu-id="e9f22-120">Para crear la clase Loan</span><span class="sxs-lookup"><span data-stu-id="e9f22-120">To create the Loan class</span></span>  
  
1.  <span data-ttu-id="e9f22-121">Cree un nuevo proyecto de bibliotecas de clases y denomínelo "LoanClass".</span><span class="sxs-lookup"><span data-stu-id="e9f22-121">Create a new Class Library project and name it "LoanClass".</span></span> <span data-ttu-id="e9f22-122">Para más información, vea [Crear soluciones y proyectos](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="e9f22-122">For more information, see [Creating Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>  
  
2.  <span data-ttu-id="e9f22-123">En el **Explorador de soluciones**, abra el menú contextual del archivo Class1 y pulse **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="e9f22-123">In **Solution Explorer**, open the shortcut menu for the Class1 file and choose **Rename**.</span></span> <span data-ttu-id="e9f22-124">Cambie el nombre del archivo a `Loan` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e9f22-124">Rename the file to `Loan` and press ENTER.</span></span> <span data-ttu-id="e9f22-125">Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `Loan`.</span><span class="sxs-lookup"><span data-stu-id="e9f22-125">Renaming the file will also rename the class to `Loan`.</span></span>  
  
3.  <span data-ttu-id="e9f22-126">Agregue los siguientes miembros públicos a la clase:</span><span class="sxs-lookup"><span data-stu-id="e9f22-126">Add the following public members to the class:</span></span>  
  
    ```csharp  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
        public double LoanAmount {get; set;}  
        public double InterestRate {get; set;}  
        public int Term {get; set;}  
  
        private string p_Customer;  
        public string Customer  
        {  
            get { return p_Customer; }  
            set   
            {  
                p_Customer = value;  
                PropertyChanged(this,  
                  new System.ComponentModel.PropertyChangedEventArgs("Customer"));  
            }  
        }  
  
        public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
  
        public Loan(double loanAmount,  
                    double interestRate,  
                    int term,  
                    string customer)  
        {  
            this.LoanAmount = loanAmount;  
            this.InterestRate = interestRate;  
            this.Term = term;  
            p_Customer = customer;  
        }  
    }  
    ```  
  
 <span data-ttu-id="e9f22-127">También tendrá que crear una aplicación sencilla que use la clase `Loan`.</span><span class="sxs-lookup"><span data-stu-id="e9f22-127">You will also have to create a simple application that uses the `Loan` class.</span></span>  
  
### <a name="to-create-a-test-application"></a><span data-ttu-id="e9f22-128">Para crear una aplicación de prueba</span><span class="sxs-lookup"><span data-stu-id="e9f22-128">To create a test application</span></span>  
  
1.  <span data-ttu-id="e9f22-129">Para agregar un proyecto de Aplicación de Windows Forms a su solución, en el menú **Archivo**, pulse **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e9f22-129">To add a Windows Forms Application project to your solution, on the **File** menu, choose **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="e9f22-130">En el cuadro de diálogo **Agregar nuevo proyecto**, pulse **Aplicación de Windows Forms** y escriba `LoanApp` como el nombre del proyecto y, después, haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-130">In the **Add New Project** dialog box, choose **Windows Forms Application**, and enter `LoanApp` as the name of the project, and then click **OK** to close the dialog box.</span></span>  
  
3.  <span data-ttu-id="e9f22-131">En el **Explorador de soluciones**, elija el proyecto de LoanApp.</span><span class="sxs-lookup"><span data-stu-id="e9f22-131">In **Solution Explorer**, choose the LoanApp project.</span></span>  
  
4.  <span data-ttu-id="e9f22-132">En el menú **Proyecto**, seleccione **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="e9f22-132">On the **Project** menu, choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="e9f22-133">En el menú **Proyecto** , elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e9f22-133">On the **Project** menu, choose **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="e9f22-134">En el cuadro de diálogo **Agregar referencia**, pulse la pestaña **Proyectos** y, después, elija el proyecto de LoanClass.</span><span class="sxs-lookup"><span data-stu-id="e9f22-134">In the **Add Reference** dialog box, choose the **Projects** tab and then choose the LoanClass project.</span></span>  
  
7.  <span data-ttu-id="e9f22-135">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-135">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="e9f22-136">En el diseñador, agregue cuatro controles <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="e9f22-136">In the designer, add four <xref:System.Windows.Forms.TextBox> controls to the form.</span></span>  
  
9. <span data-ttu-id="e9f22-137">En el Editor de códigos, agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="e9f22-137">In the Code Editor, add the following code:</span></span>  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
10. <span data-ttu-id="e9f22-138">Agregue un controlador de eventos para el evento `PropertyChanged` al formulario con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9f22-138">Add an event handler for the `PropertyChanged` event to the form by using the following code:</span></span>  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 <span data-ttu-id="e9f22-139">En este punto, podrá compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9f22-139">At this point, you can build and run the application.</span></span> <span data-ttu-id="e9f22-140">Tenga en cuenta que los valores predeterminados de la clase `Loan` aparecen en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-140">Note that the default values from the `Loan` class appear in the text boxes.</span></span> <span data-ttu-id="e9f22-141">Intente cambiar el valor de la tasa de interés de 7,5 a 7,1 y, después, cierre la aplicación y ejecútela de nuevo; el valor vuelve a ser el valor predeterminado de 7,5.</span><span class="sxs-lookup"><span data-stu-id="e9f22-141">Try to change the interest-rate value from 7.5 to 7.1, and then close the application and run it again—the value reverts to the default of 7.5.</span></span>  
  
 <span data-ttu-id="e9f22-142">En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9f22-142">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="e9f22-143">En lugar de hacer que el usuario actualice la tasa de interés cada vez que se ejecuta la aplicación, es mejor conservar la tasa de interés más reciente entre instancias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9f22-143">Rather than making the user update the interest rate every time that the application runs, it is better to preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="e9f22-144">En el paso siguiente, hará esto agregando la serialización a la clase Loan.</span><span class="sxs-lookup"><span data-stu-id="e9f22-144">In the next step, you will do just that by adding serialization to the Loan class.</span></span>  
  
## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="e9f22-145">Usar la serialización para conservar el objeto</span><span class="sxs-lookup"><span data-stu-id="e9f22-145">Using Serialization to Persist the Object</span></span>  
 <span data-ttu-id="e9f22-146">Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="e9f22-146">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span>  
  
### <a name="to-mark-a-class-as-serializable"></a><span data-ttu-id="e9f22-147">Para marcar una clase como serializable</span><span class="sxs-lookup"><span data-stu-id="e9f22-147">To mark a class as serializable</span></span>  
  
-   <span data-ttu-id="e9f22-148">Cambie la declaración de clase para la clase Loan de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9f22-148">Change the class declaration for the Loan class as follows:</span></span>  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 <span data-ttu-id="e9f22-149">El atributo `Serializable` indica al compilador que todo el contenido de la clase puede conservarse en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-149">The `Serializable` attribute tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="e9f22-150">Como el evento `PropertyChanged` está controlado por un objeto de Windows Forms, no puede serializarse.</span><span class="sxs-lookup"><span data-stu-id="e9f22-150">Because the `PropertyChanged` event is handled by a Windows Form object, it cannot be serialized.</span></span> <span data-ttu-id="e9f22-151">El atributo `NonSerialized` puede usarse para marcar miembros de clase que no deben conservarse.</span><span class="sxs-lookup"><span data-stu-id="e9f22-151">The `NonSerialized` attribute can be used to mark class members that should not be persisted.</span></span>  
  
### <a name="to-prevent-a-member-from-being-serialized"></a><span data-ttu-id="e9f22-152">Para evitar que un miembro se serialice</span><span class="sxs-lookup"><span data-stu-id="e9f22-152">To prevent a member from being serialized</span></span>  
  
-   <span data-ttu-id="e9f22-153">Cambie la declaración del evento `PropertyChanged` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9f22-153">Change the declaration for the `PropertyChanged` event as follows:</span></span>  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 <span data-ttu-id="e9f22-154">El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp.</span><span class="sxs-lookup"><span data-stu-id="e9f22-154">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="e9f22-155">Para serializar la clase y escribirla en un archivo, usará los espacios de nombres <xref:System.IO> y <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="e9f22-155">In order to serialize the class and write it to a file, you will use the <xref:System.IO> and <xref:System.Xml.Serialization> namespaces.</span></span> <span data-ttu-id="e9f22-156">Para evitar escribir los nombres completos, puede agregar referencias a las bibliotecas de clase necesarias.</span><span class="sxs-lookup"><span data-stu-id="e9f22-156">To avoid typing the fully qualified names, you can add references to the necessary class libraries.</span></span>  
  
### <a name="to-add-references-to-namespaces"></a><span data-ttu-id="e9f22-157">Para agregar referencias a los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="e9f22-157">To add references to namespaces</span></span>  
  
-   <span data-ttu-id="e9f22-158">Agregue las instrucciones siguientes en la parte superior de la clase `Form1`:</span><span class="sxs-lookup"><span data-stu-id="e9f22-158">Add the following statements to the top of the `Form1` class:</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     <span data-ttu-id="e9f22-159">En este caso, está usando un formateador binario para guardar el objeto en un formato binario.</span><span class="sxs-lookup"><span data-stu-id="e9f22-159">In this case, you are using a binary formatter to save the object in a binary format.</span></span>  
  
 <span data-ttu-id="e9f22-160">El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea.</span><span class="sxs-lookup"><span data-stu-id="e9f22-160">The next step is to add code to deserialize the object from the file when the object is created.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="e9f22-161">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="e9f22-161">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="e9f22-162">Agregue una constante a la clase para el nombre de archivo de los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="e9f22-162">Add a constant to the class for the serialized data's file name.</span></span>  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  <span data-ttu-id="e9f22-163">Modifique el código en el procedimiento de evento `Form1_Load` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e9f22-163">Modify the code in the `Form1_Load` event procedure as follows:</span></span>  
  
    ```csharp  
    private LoanClass.Loan TestLoan = new LoanClass.Loan(10000.0, 0.075, 36, "Neil Black");  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        if (File.Exists(FileName))  
        {  
            Stream TestFileStream = File.OpenRead(FileName);  
            BinaryFormatter deserializer = new BinaryFormatter();  
            TestLoan = (LoanClass.Loan)deserializer.Deserialize(TestFileStream);  
            TestFileStream.Close();  
        }  
  
        TestLoan.PropertyChanged += this.CustomerPropertyChanged;  
  
        textBox1.Text = TestLoan.LoanAmount.ToString();  
        textBox2.Text = TestLoan.InterestRate.ToString();  
        textBox3.Text = TestLoan.Term.ToString();  
        textBox4.Text = TestLoan.Customer;  
    }  
    ```  
  
     <span data-ttu-id="e9f22-164">Tenga en cuenta que primero debe comprobar que existe el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-164">Note that you first must check that the file exists.</span></span> <span data-ttu-id="e9f22-165">Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-165">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="e9f22-166">También necesita convertir del tipo de secuencia al tipo de objeto Loan.</span><span class="sxs-lookup"><span data-stu-id="e9f22-166">You also need to convert from the stream type to the Loan object type.</span></span>  
  
 <span data-ttu-id="e9f22-167">Después, debe agregar código para guardar los datos que se han escrito en los cuadros de texto en la clase `Loan` y, luego, debe serializar la clase en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-167">Next you must add code to save the data entered in the text boxes to the `Loan` class, and then you must serialize the class to a file.</span></span>  
  
### <a name="to-save-the-data-and-serialize-the-class"></a><span data-ttu-id="e9f22-168">Para guardar los datos y serializar la clase</span><span class="sxs-lookup"><span data-stu-id="e9f22-168">To save the data and serialize the class</span></span>  
  
-   <span data-ttu-id="e9f22-169">Agregue el código siguiente al procedimiento de eventos `Form1_FormClosing`:</span><span class="sxs-lookup"><span data-stu-id="e9f22-169">Add the following code to the `Form1_FormClosing` event procedure:</span></span>  
  
    ```csharp  
    private void Form1_FormClosing(object sender, FormClosingEventArgs e)  
    {  
        TestLoan.LoanAmount = Convert.ToDouble(textBox1.Text);  
        TestLoan.InterestRate = Convert.ToDouble(textBox2.Text);  
        TestLoan.Term = Convert.ToInt32(textBox3.Text);  
        TestLoan.Customer = textBox4.Text;  
  
        Stream TestFileStream = File.Create(FileName);  
        BinaryFormatter serializer = new BinaryFormatter();  
        serializer.Serialize(TestFileStream, TestLoan);  
        TestFileStream.Close();  
    }  
    ```  
  
 <span data-ttu-id="e9f22-170">En este punto, podrá compilar y ejecutar la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-170">At this point, you can again build and run the application.</span></span> <span data-ttu-id="e9f22-171">Inicialmente, los valores predeterminados aparecen en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-171">Initially, the default values appear in the text boxes.</span></span> <span data-ttu-id="e9f22-172">Pruebe a cambiar los valores y escriba un nombre en el cuarto cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-172">Try to change the values and enter a name in the fourth text box.</span></span> <span data-ttu-id="e9f22-173">Cierre la aplicación y, después, ejecútela de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9f22-173">Close the application and then run it again.</span></span> <span data-ttu-id="e9f22-174">Tenga en cuenta que los valores nuevos aparecen ahora en los cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="e9f22-174">Note that the new values now appear in the text boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f22-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9f22-175">See Also</span></span>  
 [<span data-ttu-id="e9f22-176">Serialización (C#)</span><span class="sxs-lookup"><span data-stu-id="e9f22-176">Serialization (C# )</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [<span data-ttu-id="e9f22-177">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e9f22-177">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
