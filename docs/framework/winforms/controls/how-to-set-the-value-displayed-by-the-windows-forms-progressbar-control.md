---
title: Establecer el valor mostrado por ProgressBar Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141816"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Cómo: Establecer el valor que muestra el control ProgressBar de formularios Windows Forms
> [!IMPORTANT]
> El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 .NET Framework proporciona varias formas diferentes de mostrar <xref:System.Windows.Forms.ProgressBar> un valor determinado dentro del control. El enfoque que elija dependerá de la tarea en cuestión o del problema que esté resolviendo. En la tabla siguiente se muestran los enfoques que puede elegir.  
  
|Enfoque|Descripción|  
|--------------|-----------------|  
|Establezca el valor <xref:System.Windows.Forms.ProgressBar> del control directamente.|Este enfoque es útil para las tareas en las que conoce el total del elemento medido que estará implicado, como la lectura de registros de un origen de datos. Además, si solo necesita establecer el valor una o dos veces, esta es una manera fácil de hacerlo. Por último, utilice este proceso si necesita disminuir el valor mostrado por la barra de progreso.|  
|Aumente <xref:System.Windows.Forms.ProgressBar> la visualización en un valor fijo.|Este enfoque es útil cuando se muestra un recuento simple entre el mínimo y el máximo, como el tiempo transcurrido o el número de archivos que se han procesado de un total conocido.|  
|Aumente <xref:System.Windows.Forms.ProgressBar> la visualización por un valor que varíe.|Este enfoque es útil cuando necesita cambiar el valor mostrado varias veces en diferentes cantidades. Un ejemplo sería mostrar la cantidad de espacio en disco duro que se consume al escribir una serie de archivos en el disco.|  
  
 La forma más directa de establecer el valor mostrado <xref:System.Windows.Forms.ProgressBar.Value%2A> por una barra de progreso es estableciendo la propiedad. Esto se puede hacer en tiempo de diseño o en tiempo de ejecución.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Para establecer el valor ProgressBar directamente  
  
1. Establezca <xref:System.Windows.Forms.ProgressBar> los valores <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> y los del control.  
  
2. En el código, establezca <xref:System.Windows.Forms.ProgressBar.Value%2A> la propiedad del control en un valor entero entre los valores mínimo y máximo que ha establecido.  
  
    > [!NOTE]
    > Si establece <xref:System.Windows.Forms.ProgressBar.Value%2A> la propiedad fuera de <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> los límites establecidos <xref:System.ArgumentException> por las propiedades y, el control produce una excepción.  
  
     En el ejemplo de código <xref:System.Windows.Forms.ProgressBar> siguiente se muestra cómo establecer el valor directamente. El código lee los registros de un origen de datos y actualiza la barra de progreso y la etiqueta cada vez que se lee un registro de datos. En este ejemplo se requiere <xref:System.Windows.Forms.Label> que <xref:System.Windows.Forms.ProgressBar> el formulario tenga un control, `CustomerRow` `FirstName` un `LastName` control y una tabla de datos con una fila llamada con campos.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     Si muestra el progreso que se procede por un intervalo fijo, puede establecer <xref:System.Windows.Forms.ProgressBar> el valor y, a continuación, llamar a un método que aumenta el valor del control por ese intervalo. Esto es útil para temporizadores y otros escenarios en los que no se mide el progreso como un porcentaje del todo.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Para aumentar la barra de progreso en un valor fijo  
  
1. Establezca <xref:System.Windows.Forms.ProgressBar> los valores <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> y los del control.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.ProgressBar.Step%2A> del control en un entero que represente la cantidad para aumentar el valor mostrado de la barra de progreso.  
  
3. Llame <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> al método para cambiar el valor mostrado <xref:System.Windows.Forms.ProgressBar.Step%2A> por el importe establecido en la propiedad.  
  
     En el ejemplo de código siguiente se muestra cómo una barra de progreso puede mantener un recuento de los archivos en una operación de copia.  
  
     En el ejemplo siguiente, a medida que cada archivo se lee en la memoria, la barra de progreso y la etiqueta se actualizan para reflejar el total de archivos leídos. Este ejemplo requiere que el <xref:System.Windows.Forms.Label> formulario <xref:System.Windows.Forms.ProgressBar> tenga un control y un control.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     Por último, puede aumentar el valor mostrado por una barra de progreso para que cada aumento sea una cantidad única. Esto es útil cuando realiza un seguimiento de una serie de operaciones únicas, como escribir archivos de diferentes tamaños en un disco duro o medir el progreso como un porcentaje del conjunto.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Para aumentar la barra de progreso por un valor dinámico  
  
1. Establezca <xref:System.Windows.Forms.ProgressBar> los valores <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> y los del control.  
  
2. Llame <xref:System.Windows.Forms.ProgressBar.Increment%2A> al método para cambiar el valor mostrado por un entero que especifique.  
  
     En el ejemplo de código siguiente se muestra cómo una barra de progreso puede calcular cuánto espacio en disco se ha utilizado durante una operación de copia.  
  
     En el ejemplo siguiente, a medida que cada archivo se escribe en el disco duro, la barra de progreso y la etiqueta se actualizan para reflejar la cantidad de espacio disponible en el disco duro. Este ejemplo requiere que el <xref:System.Windows.Forms.Label> formulario <xref:System.Windows.Forms.ProgressBar> tenga un control y un control.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Información general sobre ProgressBar (Control)](progressbar-control-overview-windows-forms.md)
- [Control ProgressBar](progressbar-control-windows-forms.md)
