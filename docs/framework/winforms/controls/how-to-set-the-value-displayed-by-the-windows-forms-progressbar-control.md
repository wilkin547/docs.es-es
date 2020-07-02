---
title: Establecer el valor mostrado por el control ProgressBar
description: Obtenga información sobre cómo establecer el valor que muestra el control ProgressBar Windows Forms. Hay varios enfoques que puede usar.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 75fe1b416636471d797a39134f45a05c972c9d39
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618108"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Procedimiento para establecer el valor que muestra el control ProgressBar de formularios Windows Forms
> [!IMPORTANT]
> El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El .NET Framework proporciona varias maneras de mostrar un valor determinado en el <xref:System.Windows.Forms.ProgressBar> control. El método que elija dependerá de la tarea que esté disponible o del problema que esté resolviendo. En la tabla siguiente se muestran los enfoques que puede elegir.  
  
|Enfoque|Descripción|  
|--------------|-----------------|  
|Establezca el valor del <xref:System.Windows.Forms.ProgressBar> control directamente.|Este enfoque es útil para las tareas en las que se conoce el total del elemento medido que va a ser implicado, como la lectura de registros de un origen de datos. Además, si solo necesita establecer el valor una o dos veces, se trata de una manera fácil de hacerlo. Por último, use este proceso si necesita reducir el valor mostrado por la barra de progreso.|  
|Aumentar la <xref:System.Windows.Forms.ProgressBar> presentación en un valor fijo.|Este enfoque es útil cuando se muestra un recuento simple entre el mínimo y el máximo, como el tiempo transcurrido o el número de archivos que se han procesado fuera de un total conocido.|  
|Aumentar la <xref:System.Windows.Forms.ProgressBar> presentación en un valor que varíe.|Este enfoque es útil cuando es necesario cambiar el valor mostrado varias veces en diferentes cantidades. Un ejemplo sería Mostrar la cantidad de espacio en disco duro consumido al escribir una serie de archivos en el disco.|  
  
 La forma más directa de establecer el valor que se muestra en una barra de progreso es establecer la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. Esto puede hacerse en tiempo de diseño o en tiempo de ejecución.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Para establecer el valor de ProgressBar directamente  
  
1. Establezca los <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valores y del control <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .  
  
2. En el código, establezca la propiedad del control <xref:System.Windows.Forms.ProgressBar.Value%2A> en un valor entero entre los valores mínimo y máximo que ha establecido.  
  
    > [!NOTE]
    > Si establece la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad fuera de los límites establecidos por las <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedades y, el control produce una <xref:System.ArgumentException> excepción.  
  
     En el ejemplo de código siguiente se muestra cómo establecer el <xref:System.Windows.Forms.ProgressBar> valor directamente. El código Lee los registros de un origen de datos y actualiza la barra de progreso y la etiqueta cada vez que se lee un registro de datos. Este ejemplo requiere que el formulario tenga un <xref:System.Windows.Forms.Label> control, un <xref:System.Windows.Forms.ProgressBar> control y una tabla de datos con una fila denominada `CustomerRow` con `FirstName` `LastName` los campos y.  
  
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
  
     Si va a mostrar el progreso que sigue un intervalo fijo, puede establecer el valor y, a continuación, llamar a un método que aumente el <xref:System.Windows.Forms.ProgressBar> valor del control en ese intervalo. Esto resulta útil para los temporizadores y otros escenarios en los que no se mide el progreso como un porcentaje del total.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Para aumentar la barra de progreso con un valor fijo  
  
1. Establezca los <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valores y del control <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .  
  
2. Establezca la propiedad del control <xref:System.Windows.Forms.ProgressBar.Step%2A> en un entero que represente la cantidad en la que se va a aumentar el valor mostrado de la barra de progreso.  
  
3. Llame al <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> método para cambiar el valor mostrado por la cantidad establecida en la <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad.  
  
     En el ejemplo de código siguiente se muestra cómo una barra de progreso puede mantener un recuento de los archivos en una operación de copia.  
  
     En el ejemplo siguiente, a medida que cada archivo se lee en la memoria, la barra de progreso y la etiqueta se actualizan para reflejar el número total de archivos leídos. Este ejemplo requiere que el formulario tenga un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.  
  
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
  
     Por último, puede aumentar el valor que se muestra en una barra de progreso para que cada aumento sea una cantidad única. Esto resulta útil cuando se realiza un seguimiento de una serie de operaciones únicas, como escribir archivos de distintos tamaños en un disco duro o medir el progreso como un porcentaje del total.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Para aumentar la barra de progreso mediante un valor dinámico  
  
1. Establezca los <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> valores y del control <xref:System.Windows.Forms.ProgressBar.Maximum%2A> .  
  
2. Llame al <xref:System.Windows.Forms.ProgressBar.Increment%2A> método para cambiar el valor mostrado por un entero que especifique.  
  
     En el ejemplo de código siguiente se muestra cómo una barra de progreso puede calcular cuánto espacio en disco se ha usado durante una operación de copia.  
  
     En el ejemplo siguiente, a medida que cada archivo se escribe en el disco duro, la barra de progreso y la etiqueta se actualizan para reflejar la cantidad de espacio en disco duro disponible. Este ejemplo requiere que el formulario tenga un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Información general sobre el control ProgressBar](progressbar-control-overview-windows-forms.md)
- [Control ProgressBar](progressbar-control-windows-forms.md)
