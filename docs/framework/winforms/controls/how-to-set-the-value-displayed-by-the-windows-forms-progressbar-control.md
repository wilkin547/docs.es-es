---
title: Filtrar para establecer el valor que muestra el control ProgressBar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300481"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Filtrar para establecer el valor que muestra el control ProgressBar de formularios Windows Forms
> [!IMPORTANT]
>  El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] le ofrece varias formas de mostrar un valor determinado en el <xref:System.Windows.Forms.ProgressBar> control. Método que elija dependerá de la tarea en cuestión o el problema que va a resolver. La siguiente tabla muestra los enfoques que puede elegir.  
  
|Enfoque|Descripción|  
|--------------|-----------------|  
|Establezca el valor de la <xref:System.Windows.Forms.ProgressBar> controlar directamente.|Este enfoque es útil para tareas donde se sabe el total del elemento medido que va a participar, como la lectura de registros desde un origen de datos. Además, si solo tiene que establecer el valor de una o dos veces, esto es una manera fácil de hacerlo. Por último, use este proceso si tiene que disminuya el valor mostrado por la barra de progreso.|  
|Aumentar el <xref:System.Windows.Forms.ProgressBar> mostrar mediante un valor fijo.|Este enfoque es útil cuando se va a mostrar un recuento simple entre los valores mínimo y máximo, por ejemplo, tiempo transcurrido o el número de archivos que se han procesado de un total conocido.|  
|Aumentar el <xref:System.Windows.Forms.ProgressBar> mostrar en un valor variable.|Este enfoque es útil cuando necesita cambiar el valor mostrado un número de veces en cantidades diferentes. Un ejemplo podría mostrar la cantidad de espacio en disco consumido al escribir una serie de archivos en el disco.|  
  
 La forma más directa para establecer el valor que se muestra una barra de progreso está estableciendo el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad. Esto puede hacerse en tiempo de diseño o en tiempo de ejecución.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Para establecer el valor de ProgressBar directamente  
  
1. Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.  
  
2. En el código, establezca el control <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad en un valor entero entre los valores mínimos y máximo que ha establecido.  
  
    > [!NOTE]
    >  Si establece la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad fuera de los límites establecidos por el <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedades, el control genera un <xref:System.ArgumentException> excepción.  
  
     En el ejemplo de código siguiente se muestra cómo establecer el <xref:System.Windows.Forms.ProgressBar> valor directamente. El código lee los registros de un origen de datos y la barra de progreso y la etiqueta actualiza cada vez que se lee un registro de datos. Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> (control), un <xref:System.Windows.Forms.ProgressBar> control y una tabla de datos con una fila denominada `CustomerRow` con `FirstName` y `LastName` campos.  
  
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
  
     Si desea mostrar el progreso que se realiza en un intervalo fijo, puede establecer el valor y, a continuación, llame al método que aumenta la <xref:System.Windows.Forms.ProgressBar> valor del control en ese intervalo. Esto es útil para los temporizadores y otros escenarios donde no se mide el progreso como un porcentaje del total.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Para aumentar la barra de progreso en un valor fijo  
  
1. Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.  
  
2. Establecer el control <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad en un entero que representa la cantidad para aumentar la barra de progreso muestra el valor.  
  
3. Llame a la <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> método para cambiar el valor mostrado por el número establecido en el <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad.  
  
     En el ejemplo de código siguiente se muestra cómo una barra de progreso puede mantener un recuento de los archivos en una operación de copia.  
  
     En el ejemplo siguiente, tal como se lee cada archivo en la memoria, la barra de progreso y la etiqueta se actualizan para reflejar que el total de archivos de lectura. Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.  
  
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
  
     Por último, puede aumentar el valor mostrado por una barra de progreso para que cada aumento es una cantidad única. Esto es útil cuando se mantiene un seguimiento de una serie de operaciones únicas, como escribir archivos de distinto tamaño en un disco duro o medir el progreso como un porcentaje del total.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Para aumentar la barra de progreso en un valor dinámico  
  
1. Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.  
  
2. Llame a la <xref:System.Windows.Forms.ProgressBar.Increment%2A> método para cambiar el valor mostrado por un número entero que especifique.  
  
     El ejemplo de código siguiente muestra cómo una barra de progreso puede calcular cuánto espacio en disco se ha utilizado durante una operación de copia.  
  
     En el ejemplo siguiente, tal como se escribe cada archivo en el disco duro, la barra de progreso y la etiqueta se actualizan para reflejar la cantidad de espacio en disco disponible. Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.  
  
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
