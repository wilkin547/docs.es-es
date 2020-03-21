---
title: Acceso seguro a archivos y datos
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
ms.openlocfilehash: a29c2f7137440e64fbf8095f77d5d10d0505bc2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185895"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a>Acceso más seguro a archivos y datos en formularios Windows Forms
.NET Framework usa permisos para ayudar a proteger los recursos y los datos. Los lugares donde puede leer o escribir datos la aplicación dependen de los permisos concedidos a esa aplicación. Si la aplicación se ejecuta en un entorno de confianza parcial, puede que no tenga acceso a los datos o que deba cambiar la forma de acceder a los datos.  
  
 Si se encuentra con una restricción de seguridad, tiene dos opciones: declarar el permiso (si se concedió a la aplicación) o utilizar una versión de la característica escrita para funcionar en confianza parcial. Las secciones siguientes describen cómo trabajar con el acceso a archivos, a bases de datos y al Registro desde las aplicaciones que se ejecutan en un entorno de confianza parcial.  
  
> [!NOTE]
> De forma predeterminada, las herramientas que generan ClickOnceClickOnce implementaciones de forma predeterminada estas implementaciones para solicitar plena confianza de los equipos en los que se ejecutan. Si decide que desea que las ventajas de seguridad adicionales de la ejecución en confianza parcial, debe cambiar este valor predeterminado en Visual Studio o en una de las herramientas de Windows SDK (Mage.exe o MageUI.exe). Para obtener más información acerca de la seguridad de formularios Windows Forms y sobre cómo determinar el nivel de confianza adecuado para la aplicación, vea [Seguridad en Windows Forms Información general](security-in-windows-forms-overview.md).  
  
## <a name="file-access"></a>Acceso a archivos  
 La <xref:System.Security.Permissions.FileIOPermission> clase controla el acceso a archivos y carpetas en .NET Framework. De forma predeterminada, el sistema de seguridad no concede <xref:System.Security.Permissions.FileIOPermission> a los entornos de confianza parcial, como las zonas de Internet y de la intranet local. Sin embargo, una aplicación que requiera acceso a los archivos puede funcionar en estos entornos si usted modifica el diseño de la aplicación o utiliza otros métodos para acceder a los archivos. De forma predeterminada, a la zona de la intranet local se le concede el derecho a acceder a su sitio y a su directorio, para conectarse a su sitio de origen, y a leer desde su directorio de instalación. De forma predeterminada, a la zona de Internet solo se le concede el derecho a conectarse a su sitio de origen.  
  
### <a name="user-specified-files"></a>Archivos especificados por el usuario  
 Una forma de solucionar la falta de permiso para acceder a los archivos es preguntar al usuario para que proporcione información específica sobre el archivo con las clases <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>. Esta interacción del usuario ofrece cierta seguridad de cara a que la aplicación no pueda cargar de forma malintencionada archivos privados ni sobrescribir archivos importantes. Los métodos <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> y <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> proporcionan acceso de lectura y escritura a los archivos abriendo la secuencia de archivos para el archivo especificado por el usuario. Los métodos también protegen el archivo del usuario ocultando la ruta del archivo.  
  
> [!NOTE]
> Estos permisos varían en función de si la aplicación está en la zona de Internet o de la intranet. Las aplicaciones de la zona de Internet solo pueden utilizar <xref:System.Windows.Forms.OpenFileDialog>, mientras que las aplicaciones de la intranet tienen el permiso del cuadro de diálogo de archivo sin restricciones.  
  
 La clase <xref:System.Security.Permissions.FileDialogPermission> especifica qué tipo de cuadro de diálogo de archivo puede usar la aplicación. En la tabla siguiente, se muestra el valor que debe tener para utilizar cada clase de <xref:System.Windows.Forms.FileDialog>.  
  
|Clase|Valor de acceso necesario|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> No se solicita el permiso específico hasta que se llama al método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>.  
  
 El permiso para mostrar un cuadro de diálogo de archivo no implica que se conceda a la aplicación acceso total a todos los miembros de las clases <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog>. Para obtener los permisos exactos necesarios para llamar a cada método, vea el tema de referencia para ese método en la documentación de la biblioteca de clases de .NET Framework.  
  
 El siguiente ejemplo de código utiliza el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para abrir un archivo especificado por el usuario en un control <xref:System.Windows.Forms.RichTextBox>. El ejemplo requiere <xref:System.Security.Permissions.FileDialogPermission> y el valor de enumeración asociado <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A>. En el ejemplo se muestra cómo administrar <xref:System.Security.SecurityException> para determinar si la característica de guardar se debe deshabilitar. Este ejemplo requiere que el <xref:System.Windows.Forms.Form> tenga un control <xref:System.Windows.Forms.Button> denominado `ButtonOpen`, y un control <xref:System.Windows.Forms.RichTextBox> denominado `RtfBoxMain`.  
  
> [!NOTE]
> La lógica de programación de la característica de guardar no se muestra en el ejemplo.  
  
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
> En Visual C, asegúrese de agregar código para habilitar el controlador de eventos. Con el código del ejemplo anterior, el código siguiente muestra cómo habilitar el controlador de eventos.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`  
  
### <a name="other-files"></a>Otros archivos  
 A veces, necesitará leer o escribir en archivos que no especifique el usuario, por ejemplo, para conservar la configuración de la aplicación. En las zonas de Internet y de la intranet local, la aplicación no tendrá permiso para almacenar datos en un archivo local. Sin embargo, la aplicación podrá almacenar datos en un almacenamiento aislado. El almacenamiento aislado es un compartimiento de datos abstracto (no una ubicación de almacenamiento concreta) que contiene uno o varios archivos de almacenamiento aislado, denominados “almacenes”, que contienen las ubicaciones reales de los directorios donde están almacenados los datos. No son necesarios los permisos de acceso de los archivos como <xref:System.Security.Permissions.FileIOPermission>, sino que la clase <xref:System.Security.Permissions.IsolatedStoragePermission> controla los permisos del almacenamiento aislado. De forma predeterminada, las aplicaciones que se ejecutan en las zonas de Internet y de la intranet local pueden almacenar datos con el almacenamiento aislado. Sin embargo, ciertas configuraciones, como la cuota de disco, pueden variar. Para obtener más información sobre el almacenamiento aislado, consulte [Almacenamiento aislado](../../standard/io/isolated-storage.md).  
  
 En el ejemplo siguiente, se utiliza el almacenamiento aislado para escribir datos en un archivo que se encuentra en un almacén. El ejemplo requiere <xref:System.Security.Permissions.IsolatedStorageFilePermission> y el valor de enumeración <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser>. El ejemplo muestra la lectura y la escritura de valores de determinadas propiedades del control <xref:System.Windows.Forms.Button> en un archivo situado en un almacenamiento aislado. Se llama a la función `Read` después de que se inicie la aplicación, y a la función `Write` antes de que finalice la aplicación. El ejemplo requiere `Read` que `Write` las funciones <xref:System.Windows.Forms.Form> y existan como miembros de un que contiene un <xref:System.Windows.Forms.Button> control denominado `MainButton`.  
  
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
  
## <a name="database-access"></a>Acceso a la base de datos  
 Los permisos necesarios para acceder a una base de datos varían según el proveedor de la base de datos. Sin embargo, solo las aplicaciones que se ejecutan con los permisos adecuados pueden acceder a una base de datos a través de una conexión de datos. Para obtener más información acerca de los permisos necesarios para tener acceso a una base de datos, vea Seguridad de acceso de código [y ADO.NET](../data/adonet/code-access-security.md).  
  
 Si no puede acceder directamente a una base de datos porque quiere que la aplicación se ejecute en confianza parcial, puede utilizar un servicio Web como un medio alternativo para acceder a los datos. Un servicio Web es un componente de software al que se puede acceder mediante programación a través de una red. Con los servicios Web, las aplicaciones pueden compartir datos entre las zonas del grupo de código. De forma predeterminada, a las aplicaciones de las zonas de Internet y de la intranet local se les concede el derecho de acceso a sus sitios de origen, lo que les permite llamar a un servicio Web hospedado en el mismo servidor. Para obtener más información, consulte [Servicios web en ASP.NET AJAX](https://docs.microsoft.com/previous-versions/aspnet/bb398785(v=vs.100)) o Windows Communication [Foundation](../wcf/index.md).  
  
## <a name="registry-access"></a>Acceso al Registro  
 La clase <xref:System.Security.Permissions.RegistryPermission> controla el acceso al Registro del sistema operativo. De forma predeterminada, solo las aplicaciones que se ejecutan localmente pueden acceder al Registro.  <xref:System.Security.Permissions.RegistryPermission> solamente concede a una aplicación el derecho a probar el acceso al Registro. No garantiza que logre acceder porque, en cualquier caso, el sistema operativo impondrá la seguridad del Registro.  
  
 Dado que no puede acceder al Registro con confianza parcial, puede que tenga que dar con otros métodos para almacenar los datos. Al almacenar la configuración de la aplicación, utilice almacenamiento aislado en lugar del Registro. El almacenamiento aislado también puede utilizarse para almacenar otros archivos específicos de la aplicación. También puede almacenar información global de la aplicación sobre el servidor o el sitio de origen porque, de forma predeterminada, a las aplicaciones se les concede el derecho a acceder a su sitio de origen.  
  
## <a name="see-also"></a>Consulte también

- [Impresión más segura en formularios Windows Forms](more-secure-printing-in-windows-forms.md)
- [Consideraciones de seguridad adicionales en Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Información general sobre la seguridad en formularios Windows Forms](security-in-windows-forms-overview.md)
- [Seguridad en los formularios Windows Forms](windows-forms-security.md)
- [Mage.exe (Herramienta de generación y edición de manifiestos)](../tools/mage-exe-manifest-generation-and-editing-tool.md)
- [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
