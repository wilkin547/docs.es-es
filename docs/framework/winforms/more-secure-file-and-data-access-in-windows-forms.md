---
title: Acceso más seguro a archivos y datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 49ba1919f68f35e9d72b012540b785e05c307c39
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743753"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="4783e-102">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4783e-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="4783e-103">El .NET Framework usa permisos para ayudar a proteger los recursos y los datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="4783e-104">Los lugares donde puede leer o escribir datos la aplicación dependen de los permisos concedidos a esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="4783e-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="4783e-105">Si la aplicación se ejecuta en un entorno de confianza parcial, puede que no tenga acceso a los datos o que deba cambiar la forma de acceder a los datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="4783e-106">Si se encuentra con una restricción de seguridad, tiene dos opciones: declarar el permiso (si se concedió a la aplicación) o utilizar una versión de la característica escrita para funcionar en confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4783e-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="4783e-107">Las secciones siguientes describen cómo trabajar con el acceso a archivos, a bases de datos y al Registro desde las aplicaciones que se ejecutan en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4783e-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4783e-108">De forma predeterminada, las herramientas que generan implementaciones ClickOnce implementan estas implementaciones de forma predeterminada para solicitar plena confianza de los equipos en los que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="4783e-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="4783e-109">Si decide que desea que las ventajas de seguridad agregadas se ejecuten en confianza parcial, debe cambiar este valor predeterminado en Visual Studio o en una de las herramientas de Windows SDK (Mage. exe o MageUI. exe).</span><span class="sxs-lookup"><span data-stu-id="4783e-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="4783e-110">Para obtener más información sobre la seguridad de Windows Forms y sobre cómo determinar el nivel de confianza adecuado para su aplicación, consulte [seguridad en Windows Forms introducción](security-in-windows-forms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4783e-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="4783e-111">Acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="4783e-111">File Access</span></span>  
 <span data-ttu-id="4783e-112">La clase <xref:System.Security.Permissions.FileIOPermission> controla el acceso a archivos y carpetas en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4783e-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="4783e-113">De forma predeterminada, el sistema de seguridad no concede <xref:System.Security.Permissions.FileIOPermission> a los entornos de confianza parcial, como las zonas de Internet y de la intranet local.</span><span class="sxs-lookup"><span data-stu-id="4783e-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="4783e-114">Sin embargo, una aplicación que requiera acceso a los archivos puede funcionar en estos entornos si usted modifica el diseño de la aplicación o utiliza otros métodos para acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="4783e-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="4783e-115">De forma predeterminada, a la zona de la intranet local se le concede el derecho a acceder a su sitio y a su directorio, para conectarse a su sitio de origen, y a leer desde su directorio de instalación.</span><span class="sxs-lookup"><span data-stu-id="4783e-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="4783e-116">De forma predeterminada, a la zona de Internet solo se le concede el derecho a conectarse a su sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="4783e-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="4783e-117">Archivos especificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="4783e-117">User-Specified Files</span></span>  
 <span data-ttu-id="4783e-118">Una forma de solucionar la falta de permiso para acceder a los archivos es preguntar al usuario para que proporcione información específica sobre el archivo con las clases <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="4783e-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="4783e-119">Esta interacción del usuario ofrece cierta seguridad de cara a que la aplicación no pueda cargar de forma malintencionada archivos privados ni sobrescribir archivos importantes.</span><span class="sxs-lookup"><span data-stu-id="4783e-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="4783e-120">Los métodos <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> y <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> proporcionan acceso de lectura y escritura a los archivos abriendo la secuencia de archivos para el archivo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4783e-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="4783e-121">Los métodos también protegen el archivo del usuario ocultando la ruta del archivo.</span><span class="sxs-lookup"><span data-stu-id="4783e-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4783e-122">Estos permisos varían en función de si la aplicación está en la zona de Internet o de la intranet.</span><span class="sxs-lookup"><span data-stu-id="4783e-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="4783e-123">Las aplicaciones de la zona de Internet solo pueden utilizar <xref:System.Windows.Forms.OpenFileDialog>, mientras que las aplicaciones de la intranet tienen el permiso del cuadro de diálogo de archivo sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="4783e-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="4783e-124">La clase <xref:System.Security.Permissions.FileDialogPermission> especifica qué tipo de cuadro de diálogo de archivo puede usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4783e-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="4783e-125">En la tabla siguiente, se muestra el valor que debe tener para utilizar cada clase de <xref:System.Windows.Forms.FileDialog>.</span><span class="sxs-lookup"><span data-stu-id="4783e-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="4783e-126">Clase</span><span class="sxs-lookup"><span data-stu-id="4783e-126">Class</span></span>|<span data-ttu-id="4783e-127">Valor de acceso necesario</span><span class="sxs-lookup"><span data-stu-id="4783e-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="4783e-128">No se solicita el permiso específico hasta que se llama al método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="4783e-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="4783e-129">El permiso para mostrar un cuadro de diálogo de archivo no implica que se conceda a la aplicación acceso total a todos los miembros de las clases <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog>.</span><span class="sxs-lookup"><span data-stu-id="4783e-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="4783e-130">Para obtener los permisos exactos necesarios para llamar a cada método, vea el tema de referencia de ese método en la documentación de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4783e-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="4783e-131">El siguiente ejemplo de código utiliza el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para abrir un archivo especificado por el usuario en un control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="4783e-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4783e-132">El ejemplo requiere <xref:System.Security.Permissions.FileDialogPermission> y el valor de enumeración asociado <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="4783e-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="4783e-133">En el ejemplo se muestra cómo administrar <xref:System.Security.SecurityException> para determinar si la característica de guardar se debe deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="4783e-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="4783e-134">Este ejemplo requiere que el <xref:System.Windows.Forms.Form> tenga un control <xref:System.Windows.Forms.Button> denominado `ButtonOpen`, y un control <xref:System.Windows.Forms.RichTextBox> denominado `RtfBoxMain`.</span><span class="sxs-lookup"><span data-stu-id="4783e-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4783e-135">La lógica de programación de la característica de guardar no se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4783e-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="4783e-136">En Visual C#, asegúrese de agregar código para habilitar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="4783e-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="4783e-137">Con el código del ejemplo anterior, el código siguiente muestra cómo habilitar el controlador de eventos.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="4783e-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="4783e-138">Otros archivos</span><span class="sxs-lookup"><span data-stu-id="4783e-138">Other Files</span></span>  
 <span data-ttu-id="4783e-139">A veces, necesitará leer o escribir en archivos que no especifique el usuario, por ejemplo, para conservar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4783e-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="4783e-140">En las zonas de Internet y de la intranet local, la aplicación no tendrá permiso para almacenar datos en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="4783e-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="4783e-141">Sin embargo, la aplicación podrá almacenar datos en un almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="4783e-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="4783e-142">El almacenamiento aislado es un compartimiento de datos abstracto (no una ubicación de almacenamiento concreta) que contiene uno o varios archivos de almacenamiento aislado, denominados “almacenes”, que contienen las ubicaciones reales de los directorios donde están almacenados los datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="4783e-143">No son necesarios los permisos de acceso de los archivos como <xref:System.Security.Permissions.FileIOPermission>, sino que la clase <xref:System.Security.Permissions.IsolatedStoragePermission> controla los permisos del almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="4783e-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="4783e-144">De forma predeterminada, las aplicaciones que se ejecutan en las zonas de Internet y de la intranet local pueden almacenar datos con el almacenamiento aislado. Sin embargo, ciertas configuraciones, como la cuota de disco, pueden variar.</span><span class="sxs-lookup"><span data-stu-id="4783e-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="4783e-145">Para obtener más información sobre el almacenamiento aislado, consulte [almacenamiento aislado](../../standard/io/isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="4783e-145">For more information about isolated storage, see [Isolated Storage](../../standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="4783e-146">En el ejemplo siguiente, se utiliza el almacenamiento aislado para escribir datos en un archivo que se encuentra en un almacén.</span><span class="sxs-lookup"><span data-stu-id="4783e-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="4783e-147">El ejemplo requiere <xref:System.Security.Permissions.IsolatedStorageFilePermission> y el valor de enumeración <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>.</span><span class="sxs-lookup"><span data-stu-id="4783e-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="4783e-148">El ejemplo muestra la lectura y la escritura de valores de determinadas propiedades del control <xref:System.Windows.Forms.Button> en un archivo situado en un almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="4783e-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="4783e-149">Se llama a la función `Read` después de que se inicie la aplicación, y a la función `Write` antes de que finalice la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4783e-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="4783e-150">El ejemplo requiere que las funciones `Read` y `Write` existan como miembros de una <xref:System.Windows.Forms.Form> que contenga un control <xref:System.Windows.Forms.Button> denominado `MainButton`.</span><span class="sxs-lookup"><span data-stu-id="4783e-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="4783e-151">Acceso a la base de datos</span><span class="sxs-lookup"><span data-stu-id="4783e-151">Database Access</span></span>  
 <span data-ttu-id="4783e-152">Los permisos necesarios para acceder a una base de datos varían según el proveedor de la base de datos. Sin embargo, solo las aplicaciones que se ejecutan con los permisos adecuados pueden acceder a una base de datos a través de una conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="4783e-153">Para obtener más información sobre los permisos necesarios para tener acceso a una base de datos, vea [seguridad de acceso del código y ADO.net](../data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="4783e-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="4783e-154">Si no puede acceder directamente a una base de datos porque quiere que la aplicación se ejecute en confianza parcial, puede utilizar un servicio Web como un medio alternativo para acceder a los datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="4783e-155">Un servicio Web es un componente de software al que se puede acceder mediante programación a través de una red.</span><span class="sxs-lookup"><span data-stu-id="4783e-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="4783e-156">Con los servicios Web, las aplicaciones pueden compartir datos entre las zonas del grupo de código.</span><span class="sxs-lookup"><span data-stu-id="4783e-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="4783e-157">De forma predeterminada, a las aplicaciones de las zonas de Internet y de la intranet local se les concede el derecho de acceso a sus sitios de origen, lo que les permite llamar a un servicio Web hospedado en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="4783e-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="4783e-158">Para obtener más información, consulte [servicios web en ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) o [Windows Communication Foundation](../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="4783e-158">For more information see [Web Services in ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](../wcf/index.md).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="4783e-159">Acceso al Registro</span><span class="sxs-lookup"><span data-stu-id="4783e-159">Registry Access</span></span>  
 <span data-ttu-id="4783e-160">La clase <xref:System.Security.Permissions.RegistryPermission> controla el acceso al Registro del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4783e-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="4783e-161">De forma predeterminada, solo las aplicaciones que se ejecutan localmente pueden acceder al Registro.</span><span class="sxs-lookup"><span data-stu-id="4783e-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="4783e-162"><xref:System.Security.Permissions.RegistryPermission> solamente concede a una aplicación el derecho a probar el acceso al Registro. No garantiza que logre acceder porque, en cualquier caso, el sistema operativo impondrá la seguridad del Registro.</span><span class="sxs-lookup"><span data-stu-id="4783e-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="4783e-163">Dado que no puede acceder al Registro con confianza parcial, puede que tenga que dar con otros métodos para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="4783e-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="4783e-164">Al almacenar la configuración de la aplicación, utilice almacenamiento aislado en lugar del Registro.</span><span class="sxs-lookup"><span data-stu-id="4783e-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="4783e-165">El almacenamiento aislado también puede utilizarse para almacenar otros archivos específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4783e-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="4783e-166">También puede almacenar información global de la aplicación sobre el servidor o el sitio de origen porque, de forma predeterminada, a las aplicaciones se les concede el derecho a acceder a su sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="4783e-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4783e-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4783e-167">See also</span></span>

- [<span data-ttu-id="4783e-168">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4783e-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="4783e-169">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4783e-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="4783e-170">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4783e-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="4783e-171">Windows Forms Security</span><span class="sxs-lookup"><span data-stu-id="4783e-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="4783e-172">Mage.exe (Herramienta de generación y edición de manifiestos)</span><span class="sxs-lookup"><span data-stu-id="4783e-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [<span data-ttu-id="4783e-173">MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)</span><span class="sxs-lookup"><span data-stu-id="4783e-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
