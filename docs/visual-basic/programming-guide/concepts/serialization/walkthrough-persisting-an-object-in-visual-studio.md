---
title: Guardar un objeto en Visual Studio (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ff6320aee65850b8b445f445f80b4bbe2c9c254
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>Tutorial: Persistir un objeto en Visual Studio (Visual Basic)
Aunque puede establecer las propiedades de un objeto con valores predeterminados en tiempo de diseño, cualquier valor introducido en tiempo de ejecución se pierden cuando se destruye el objeto. Puede utilizar la serialización para conservar los datos de un objeto entre instancias, lo que permite almacenar valores y recuperarlos la próxima vez que se crea una instancia del objeto.  
  
> [!NOTE]
>  En Visual Basic, para almacenar datos simples, como un nombre o número, puede utilizar el `My.Settings` objeto. Para obtener más información, consulte [My.Settings (objeto)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
 En este tutorial, creará un sencillo `Loan` objeto y conservar sus datos en un archivo. A continuación, recuperará los datos desde el archivo cuando vuelve a crear el objeto.  
  
> [!IMPORTANT]
>  Este ejemplo crea un nuevo archivo, si el archivo no existe. Si una aplicación debe crear un archivo, la aplicación debe `Create` permiso para la carpeta. Los permisos se establecen usando listas de control de acceso. Si el archivo ya existe, la aplicación necesita solo `Write` permiso, un permiso menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder sólo `Read` permisos en un solo archivo (en lugar de permisos de creación para una carpeta). Además, resulta más seguro escribir datos en carpetas de usuario que en la carpeta raíz o en la carpeta archivos de programa.  
  
> [!IMPORTANT]
>  Este ejemplo almacena datos en un archivo binario. Estos formatos no deben usarse para la información confidencial, como contraseñas o información de tarjeta de crédito.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-loan-object"></a>Crear el objeto Loan  
 El primer paso es crear un `Loan` clase y una aplicación de prueba que usa la clase.  
  
### <a name="to-create-the-loan-class"></a>Para crear la clase Loan  
  
1.  Cree un nuevo proyecto de biblioteca de clases y denomínelo "LoanClass". Para más información, vea [Crear soluciones y proyectos](http://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects).  
  
2.  En **el Explorador de soluciones**, abra el menú contextual para el archivo Class1 y elija **cambiar el nombre de**. El nombre del archivo a `Loan` y presione ENTRAR. Cambiar el nombre del archivo cambiará también la clase `Loan`.  
  
3.  Agregue a los siguientes miembros públicos a la clase:  
  
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
  
 También tendrá que crear una aplicación simple que usa el `Loan` clase.  
  
### <a name="to-create-a-test-application"></a>Para crear una aplicación de prueba  
  
1.  Para agregar un proyecto de aplicación de Windows Forms a la solución, en la **archivo** menú, elija **agregar**,**nuevo proyecto**.  
  
2.  En el **Agregar nuevo proyecto** cuadro de diálogo, seleccione **aplicación de Windows Forms**y escriba `LoanApp` como el nombre del proyecto y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
3.  En **el Explorador de soluciones**, seleccione el proyecto LoanApp.  
  
4.  En el **proyecto** menú, elija **establecer como proyecto de inicio**.  
  
5.  En el menú **Proyecto** , elija **Agregar referencia**.  
  
6.  En el **Agregar referencia** cuadro de diálogo, seleccione la **proyectos** ficha y, a continuación, elija el proyecto LoanClass.  
  
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
8.  En el diseñador, agregue cuatro <xref:System.Windows.Forms.TextBox>controles al formulario.</xref:System.Windows.Forms.TextBox>  
  
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
  
10. Agregar un controlador de eventos para el `PropertyChanged` evento para el formulario mediante el código siguiente:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 En este punto, puede generar y ejecutar la aplicación. Tenga en cuenta que los valores predeterminados de la `Loan` clase aparecen en los cuadros de texto. Intente cambiar el valor de la tasa de interés de 7,5 a 7.1 y, a continuación, cierre la aplicación y ejecútela de nuevo, el valor volverá a ser el valor predeterminado de 7.5.  
  
 En el mundo real, los tipos de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación. En lugar de hacer que el usuario actualice a la tasa de interés cada vez que se ejecuta la aplicación, es mejor mantener la tasa de interés más reciente entre las instancias de la aplicación. En el paso siguiente, hará exactamente eso agregando la serialización a la clase de préstamo.  
  
## <a name="using-serialization-to-persist-the-object"></a>Uso de la serialización para guardar el objeto  
 Para conservar los valores de la clase Loan, primero debe marcar la clase con el `Serializable` atributo.  
  
### <a name="to-mark-a-class-as-serializable"></a>Para marcar una clase como serializable  
  
-   Cambie la declaración de clase para la clase de la manera siguiente:  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 El `Serializable` atributo indica al compilador que todo el contenido de la clase se puede guardar en un archivo. Dado que el `PropertyChanged` evento está controlado por un objeto de formulario Windows Forms, no se puede serializar. El `NonSerialized` atributo se puede utilizar para marcar miembros de clase que no deben ser persistentes.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>Para impedir que un miembro se serialicen  
  
-   Cambie la declaración para el `PropertyChanged` eventos como sigue:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 El siguiente paso es agregar el código de serialización a la aplicación LoanApp. Para serializar la clase y escribir en un archivo, usará el <xref:System.IO>y <xref:System.Xml.Serialization>los espacios de nombres.</xref:System.Xml.Serialization> </xref:System.IO> Para evitar escribir los nombres completos, puede agregar referencias a las bibliotecas de clase necesarias.  
  
### <a name="to-add-references-to-namespaces"></a>Para agregar referencias a espacios de nombres  
  
-   Agregue las siguientes instrucciones al principio de la `Form1` clase:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     En este caso, utiliza a un formateador binario para guardar el objeto en un formato binario.  
  
 El siguiente paso es agregar código para deserializar el objeto desde el archivo cuando se crea el objeto.  
  
### <a name="to-deserialize-an-object"></a>Para deserializar un objeto  
  
1.  Agregue una constante a la clase para el nombre del archivo de datos serializados.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2.  Modifique el código de la `Form1_Load` el procedimiento de evento como sigue:  
  
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
  
     Tenga en cuenta que primero debe comprobar que el archivo existe. Si existe, cree un <xref:System.IO.Stream>clase para leer el archivo binario y un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>clase para convertir el archivo.</xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> </xref:System.IO.Stream> También necesitará convertir el tipo de secuencia para el tipo de objeto de préstamo.  
  
 A continuación debe agregar código para guardar los datos introducidos en los cuadros de texto para el `Loan` clase y, a continuación, debe serializar la clase en un archivo.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>Para guardar los datos y serializar la clase  
  
-   Agregue el código siguiente a la `Form1_FormClosing` el procedimiento de evento:  
  
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
  
 En este punto, puede volver a compilar y ejecutar la aplicación. Inicialmente, los valores predeterminados aparecen en los cuadros de texto. Pruebe a cambiar los valores y escriba un nombre en el cuarto cuadro de texto. Cierre la aplicación y, a continuación, ejecútelo de nuevo. Tenga en cuenta que los valores nuevos aparecen ahora en los cuadros de texto.  
  
## <a name="see-also"></a>Vea también  
 [Serialización (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)
