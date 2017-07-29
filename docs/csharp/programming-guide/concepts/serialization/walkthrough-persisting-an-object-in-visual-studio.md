---
title: 'Tutorial: Conservar un objeto en Visual Studio (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: a544ce46-ee25-49da-afd4-457a3d59bf63
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c8dce64c470f01f540a83f68e3861df56913e4c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-c"></a>Tutorial: Conservar un objeto en Visual Studio (C#)
Aunque puede establecer las propiedades de un objeto en los valores predeterminados en el tiempo de diseño, cualquier valor que se establezca en tiempo de ejecución se pierde cuando se destruye el objeto. Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.  
  
 En este tutorial, creará un objeto `Loan` sencillo y conservará sus datos en un archivo. Después, recuperará los datos del archivo cuando vuelva a crear el objeto.  
  
> [!IMPORTANT]
>  En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación debe crear un archivo, debe `Create` permiso para la carpeta. Los permisos se establecen mediante el uso de las listas de control de acceso. Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta). Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.  
  
> [!IMPORTANT]
>  En este ejemplo se almacenan datos en un archivo de formato binario. Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Crear el objeto Loan  
 El primer paso consiste en crear una clase `Loan` y una aplicación de prueba que use la clase.  
  
### <a name="to-create-the-loan-class"></a>Para crear la clase Loan  
  
1.  Cree un nuevo proyecto de bibliotecas de clases y denomínelo "LoanClass". Para más información, vea [Crear soluciones y proyectos](/visualstudio/ide/creating-solutions-and-projects).  
  
2.  En el **Explorador de soluciones**, abra el menú contextual del archivo Class1 y pulse **Cambiar nombre**. Cambie el nombre del archivo a `Loan` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `Loan`.  
  
3.  Agregue los siguientes miembros públicos a la clase:  
  
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
  
 También tendrá que crear una aplicación sencilla que use la clase `Loan`.  
  
### <a name="to-create-a-test-application"></a>Para crear una aplicación de prueba  
  
1.  Para agregar un proyecto de Aplicación de Windows Forms a su solución, en el menú **Archivo**, pulse **Agregar**, **Nuevo proyecto**.  
  
2.  En el cuadro de diálogo **Agregar nuevo proyecto**, pulse **Aplicación de Windows Forms** y escriba `LoanApp` como el nombre del proyecto y, después, haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3.  En el **Explorador de soluciones**, elija el proyecto de LoanApp.  
  
4.  En el menú **Proyecto**, seleccione **Establecer como proyecto de inicio**.  
  
5.  En el menú **Proyecto** , elija **Agregar referencia**.  
  
6.  En el cuadro de diálogo **Agregar referencia**, pulse la pestaña **Proyectos** y, después, elija el proyecto de LoanClass.  
  
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
8.  En el diseñador, agregue cuatro controles <xref:System.Windows.Forms.TextBox> al formulario.  
  
9. En el Editor de códigos, agregue el siguiente código:  
  
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
  
10. Agregue un controlador de eventos para el evento `PropertyChanged` al formulario con el código siguiente:  
  
    ```csharp  
    private void CustomerPropertyChanged(object sender,   
        System.ComponentModel.PropertyChangedEventArgs e)  
    {  
        MessageBox.Show(e.PropertyName + " has been changed.");  
    }  
    ```  
  
 En este punto, podrá compilar y ejecutar la aplicación. Tenga en cuenta que los valores predeterminados de la clase `Loan` aparecen en los cuadros de texto. Intente cambiar el valor de la tasa de interés de 7,5 a 7,1 y, después, cierre la aplicación y ejecútela de nuevo; el valor vuelve a ser el valor predeterminado de 7,5.  
  
 En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación. En lugar de hacer que el usuario actualice la tasa de interés cada vez que se ejecuta la aplicación, es mejor conservar la tasa de interés más reciente entre instancias de la aplicación. En el paso siguiente, hará esto agregando la serialización a la clase Loan.  
  
## <a name="using-serialization-to-persist-the-object"></a>Usar la serialización para conservar el objeto  
 Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`.  
  
### <a name="to-mark-a-class-as-serializable"></a>Para marcar una clase como serializable  
  
-   Cambie la declaración de clase para la clase Loan de la manera siguiente:  
  
    ```csharp  
    [Serializable()]  
    public class Loan : System.ComponentModel.INotifyPropertyChanged  
    {  
    ```  
  
 El atributo `Serializable` indica al compilador que todo el contenido de la clase puede conservarse en un archivo. Como el evento `PropertyChanged` está controlado por un objeto de Windows Forms, no puede serializarse. El atributo `NonSerialized` puede usarse para marcar miembros de clase que no deben conservarse.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Para evitar que un miembro se serialice  
  
-   Cambie la declaración del evento `PropertyChanged` de la manera siguiente:  
  
    ```csharp  
    [field: NonSerialized()]  
    public event System.ComponentModel.PropertyChangedEventHandler PropertyChanged;  
    ```  
  
 El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp. Para serializar la clase y escribirla en un archivo, usará los espacios de nombres <xref:System.IO> y <xref:System.Xml.Serialization>. Para evitar escribir los nombres completos, puede agregar referencias a las bibliotecas de clase necesarias.  
  
### <a name="to-add-references-to-namespaces"></a>Para agregar referencias a los espacios de nombres  
  
-   Agregue las instrucciones siguientes en la parte superior de la clase `Form1`:  
  
    ```csharp  
    using System.IO;  
    using System.Runtime.Serialization.Formatters.Binary;  
    ```  
  
     En este caso, está usando un formateador binario para guardar el objeto en un formato binario.  
  
 El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea.  
  
### <a name="to-deserialize-an-object"></a>Para deserializar un objeto  
  
1.  Agregue una constante a la clase para el nombre de archivo de los datos serializados.  
  
    ```csharp  
    const string FileName = @"..\..\SavedLoan.bin";  
    ```  
  
2.  Modifique el código en el procedimiento de evento `Form1_Load` de la manera siguiente:  
  
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
  
     Tenga en cuenta que primero debe comprobar que existe el archivo. Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo. También necesita convertir del tipo de secuencia al tipo de objeto Loan.  
  
 Después, debe agregar código para guardar los datos que se han escrito en los cuadros de texto en la clase `Loan` y, luego, debe serializar la clase en un archivo.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Para guardar los datos y serializar la clase  
  
-   Agregue el código siguiente al procedimiento de eventos `Form1_FormClosing`:  
  
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
  
 En este punto, podrá compilar y ejecutar la aplicación de nuevo. Inicialmente, los valores predeterminados aparecen en los cuadros de texto. Pruebe a cambiar los valores y escriba un nombre en el cuarto cuadro de texto. Cierre la aplicación y, después, ejecútela de nuevo. Tenga en cuenta que los valores nuevos aparecen ahora en los cuadros de texto.  
  
## <a name="see-also"></a>Vea también  
 [Serialization (C# )](../../../../csharp/programming-guide/concepts/serialization/index.md)  (Serialización (C#))  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)

