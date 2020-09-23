---
title: Conservar un objeto en Visual Studio
ms.date: 07/20/2015
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
ms.openlocfilehash: 0b2fff171164a29e6066839371fc95ad41b452f1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086470"
---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>Tutorial: Conservar un objeto en Visual Studio (Visual Basic)

Aunque puede establecer las propiedades de un objeto en los valores predeterminados en el tiempo de diseño, cualquier valor que se establezca en tiempo de ejecución se pierde cuando se destruye el objeto. Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.  
  
> [!NOTE]
> En Visual Basic, para almacenar datos simples, como un nombre o número, puede utilizar el objeto `My.Settings`. Para obtener más información, vea [My.Settings (Objeto)](../../../language-reference/objects/my-settings-object.md).  
  
 En este tutorial, creará un objeto `Loan` sencillo y conservará sus datos en un archivo. Después, recuperará los datos del archivo cuando vuelva a crear el objeto.  
  
> [!IMPORTANT]
> En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación debe crear un archivo, debe `Create` permiso para la carpeta. Los permisos se establecen mediante el uso de las listas de control de acceso. Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta). Además, es más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta Archivos de programa.  
  
> [!IMPORTANT]
> En este ejemplo se almacenan datos en un archivo binario. Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.  
  
> [!NOTE]
> Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-loan-object"></a>Crear el objeto Loan  

 El primer paso consiste en crear una clase `Loan` y una aplicación de prueba que use la clase.  
  
### <a name="to-create-the-loan-class"></a>Para crear la clase Loan  
  
1. Cree un nuevo proyecto de bibliotecas de clases y denomínelo "LoanClass". Para más información, vea [Crear soluciones y proyectos](/visualstudio/ide/creating-solutions-and-projects).  
  
2. En el **Explorador de soluciones**, abra el menú contextual del archivo Class1 y pulse **Cambiar nombre**. Cambie el nombre del archivo a `Loan` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `Loan`.  
  
3. Agregue los siguientes miembros públicos a la clase:  
  
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
  
 También tendrá que crear una aplicación sencilla que use la clase `Loan`.  
  
### <a name="to-create-a-test-application"></a>Para crear una aplicación de prueba  
  
1. Para agregar un proyecto de Aplicación de Windows Forms a su solución, en el menú **Archivo**, seleccione **Agregar**, **Nuevo proyecto**.  
  
2. En el cuadro de diálogo **Agregar nuevo proyecto**, pulse **Aplicación de Windows Forms** y escriba `LoanApp` como el nombre del proyecto y, después, haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3. En el **Explorador de soluciones**, elija el proyecto de LoanApp.  
  
4. En el menú **Proyecto**, seleccione **Establecer como proyecto de inicio**.  
  
5. En el menú **proyecto** , elija **Agregar referencia**.  
  
6. En el cuadro de diálogo **Agregar referencia**, pulse la pestaña **Proyectos** y, después, elija el proyecto de LoanClass.  
  
7. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
8. En el diseñador, agregue cuatro controles <xref:System.Windows.Forms.TextBox> al formulario.  
  
9. En el Editor de códigos, agregue el siguiente código:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. Agregue un controlador de eventos para el evento `PropertyChanged` al formulario con el código siguiente:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 En este punto, podrá compilar y ejecutar la aplicación. Tenga en cuenta que los valores predeterminados de la clase `Loan` aparecen en los cuadros de texto. Intente cambiar el valor de la tasa de interés de 7,5 a 7,1 y, después, cierre la aplicación y ejecútela de nuevo; el valor vuelve a ser el valor predeterminado de 7,5.  
  
 En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación. En lugar de hacer que el usuario actualice la tasa de interés cada vez que se ejecuta la aplicación, es mejor conservar la tasa de interés más reciente entre instancias de la aplicación. En el paso siguiente, hará esto agregando la serialización a la clase Loan.  
  
## <a name="using-serialization-to-persist-the-object"></a>Usar la serialización para conservar el objeto  

 Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`.  
  
### <a name="to-mark-a-class-as-serializable"></a>Para marcar una clase como serializable  
  
- Cambie la declaración de clase para la clase Loan de la manera siguiente:  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 El atributo `Serializable` indica al compilador que todo el contenido de la clase puede conservarse en un archivo. Como el evento `PropertyChanged` está controlado por un objeto de Windows Forms, no puede serializarse. El atributo `NonSerialized` puede usarse para marcar miembros de clase que no deben conservarse.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Para evitar que un miembro se serialice  
  
- Cambie la declaración del evento `PropertyChanged` de la manera siguiente:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp. Para serializar la clase y escribirla en un archivo, usará los espacios de nombres <xref:System.IO> y <xref:System.Xml.Serialization>. Para evitar escribir los nombres completos, puede agregar referencias a las bibliotecas de clase necesarias.  
  
### <a name="to-add-references-to-namespaces"></a>Para agregar referencias a los espacios de nombres  
  
- Agregue las instrucciones siguientes en la parte superior de la clase `Form1`:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     En este caso, está usando un formateador binario para guardar el objeto en un formato binario.  
  
 El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea.  
  
### <a name="to-deserialize-an-object"></a>Para deserializar un objeto  
  
1. Agregue una constante a la clase para el nombre de archivo de los datos serializados.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2. Modifique el código en el procedimiento de evento `Form1_Load` de la manera siguiente:  
  
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
  
     Tenga en cuenta que primero debe comprobar que existe el archivo. Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo. También necesita convertir del tipo de secuencia al tipo de objeto Loan.  
  
 Después, debe agregar código para guardar los datos que se han escrito en los cuadros de texto en la clase `Loan` y, luego, debe serializar la clase en un archivo.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Para guardar los datos y serializar la clase  
  
- Agregue el código siguiente al procedimiento de eventos `Form1_FormClosing`:  
  
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
  
 En este punto, podrá compilar y ejecutar la aplicación de nuevo. Inicialmente, los valores predeterminados aparecen en los cuadros de texto. Pruebe a cambiar los valores y escriba un nombre en el cuarto cuadro de texto. Cierre la aplicación y, después, ejecútela de nuevo. Tenga en cuenta que los valores nuevos aparecen ahora en los cuadros de texto.  
  
## <a name="see-also"></a>Vea también

- [Serialización (Visual Basic)](index.md)
- [Guía de programación en Visual Basic](../../index.md)
