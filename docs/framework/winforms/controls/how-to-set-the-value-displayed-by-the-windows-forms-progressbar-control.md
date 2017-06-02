---
title: "C&#243;mo: Establecer el valor que muestra el control ProgressBar de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Increment (método)"
  - "PerformStep (método)"
  - "controles de progreso, establecer el valor mostrado"
  - "ProgressBar (control) [Windows Forms], establecer el valor mostrado"
  - "Step (propiedad)"
  - "Value (propiedad)"
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer el valor que muestra el control ProgressBar de formularios Windows Forms
> [!IMPORTANT]
>  Aunque el control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>, este control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ofrece varias maneras de mostrar un valor determinado en el control <xref:System.Windows.Forms.ProgressBar>.  La que elija dependerá de la tarea que esté realizando o del problema que desee solucionar:  En la siguiente tabla se muestran los métodos que se pueden utilizar.  
  
|Método|Descripción|  
|------------|-----------------|  
|Definir el valor del control <xref:System.Windows.Forms.ProgressBar> directamente.|Este método es útil para tareas donde se sabe el total del elemento medido que se utilizará, como la lectura de registros de un origen de datos.  Además, si sólo tiene que definir el valor una o dos veces, ésta es una forma fácil de hacerlo.  Finalmente, utilice este proceso si necesita disminuir el valor mostrado en la barra de progreso.|  
|Aumentar el tamaño de presentación de <xref:System.Windows.Forms.ProgressBar> en un valor fijo.|Este método es útil si muestra un recuento sencillo entre el mínimo y el máximo, como el tiempo transcurrido o el número de archivos que se han procesado de un total conocido.|  
|Aumentar el tamaño de presentación de <xref:System.Windows.Forms.ProgressBar> en un valor variable.|Este método es útil si necesita cambiar el valor mostrado varias veces en cantidades diferentes.  Por ejemplo, mostrar la cantidad de espacio en disco utilizada mientras se escribe una serie de archivos en el disco.|  
  
 La manera más directa de establecer el valor mostrado por una barra de progreso consiste en establecer la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  Puede hacerlo en tiempo de diseño o en tiempo de ejecución.  
  
### Para definir el valor de ProgressBar directamente  
  
1.  Establezca los valores  <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del control <xref:System.Windows.Forms.ProgressBar>.  
  
2.  En el código, establezca la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> del control en un valor de número entero comprendido entre los valores mínimo y máximo que ha establecido.  
  
    > [!NOTE]
    >  Si establece la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> fuera de los límites establecidos por las propiedades <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>, el control produce una excepción <xref:System.ArgumentException>.  
  
     El siguiente ejemplo muestra cómo establecer el valor de <xref:System.Windows.Forms.ProgressBar> directamente.  El código lee los registros de un origen de datos y actualiza la barra y la etiqueta de progreso cada vez que se lee un registro de datos.  En este ejemplo se requiere que el formulario tenga un control <xref:System.Windows.Forms.Label>, un control <xref:System.Windows.Forms.ProgressBar> y una tabla de datos con una fila denominada `CustomerRow`  con los campos `FirstName`  y `Last Name` .  
  
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
  
     Si desea mostrar el progreso de modo que aumente en un intervalo fijo, puede establecer este valor y llamar después al método que aumenta el valor del control <xref:System.Windows.Forms.ProgressBar> en ese intervalo.  Esto es útil para temporizadores y otros escenarios donde no se mide el progreso como un porcentaje del total.  
  
### Para aumentar la barra de progreso en un valor fijo.  
  
1.  Establezca los valores  <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del control <xref:System.Windows.Forms.ProgressBar>.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ProgressBar.Step%2A> en un número entero que represente la cantidad en la que se aumentará el valor que muestra la barra de progreso.  
  
3.  Llame al método <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> para cambiar el valor mostrado con la cantidad establecida en la propiedad <xref:System.Windows.Forms.ProgressBar.Step%2A>.  
  
     El siguiente ejemplo de código muestra cómo la barra de progreso puede mantener el recuento de los archivos en una operación de copia.  
  
     Conforme se lee en memoria cada archivo, la barra y la etiqueta de progreso se actualizan para reflejar el total de archivos leídos.  Este ejemplo requiere que el formulario tenga un control <xref:System.Windows.Forms.Label> y un control <xref:System.Windows.Forms.ProgressBar>.  
  
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
  
     Por último, puede aumentar el valor que muestra una barra de progreso de manera que cada aumento sea una cantidad única.  Este método es útil cuando se realiza el seguimiento de una serie de operaciones exclusivas, como la escritura de archivos de diferente tamaño en un disco duro o la medición del progreso como un porcentaje del total.  
  
### Para aumentar la barra de progreso en un valor dinámico  
  
1.  Establezca los valores  <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> del control <xref:System.Windows.Forms.ProgressBar>.  
  
2.  Llame al método <xref:System.Windows.Forms.ProgressBar.Increment%2A> para cambiar el valor mostrado con el número entero que especifique.  
  
     El ejemplo de código siguiente muestra cómo una barra de progreso puede calcular la cantidad de espacio en disco utilizada durante una operación de copia.  
  
     En el ejemplo que sigue, conforme se escribe cada archivo en el disco duro, la barra y la etiqueta de progreso se actualizan para reflejar la cantidad de espacio en disco disponible.  Este ejemplo requiere que el formulario tenga un control <xref:System.Windows.Forms.Label> y un control <xref:System.Windows.Forms.ProgressBar>.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.ProgressBar>   
 <xref:System.Windows.Forms.ToolStripProgressBar>   
 [Información general sobre ProgressBar \(Control\)](../../../../docs/framework/winforms/controls/progressbar-control-overview-windows-forms.md)   
 [ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)