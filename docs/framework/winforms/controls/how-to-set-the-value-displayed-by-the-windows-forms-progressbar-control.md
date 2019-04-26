---
title: Procedimiento para establecer el valor que muestra el control ProgressBar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912852"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="e4b81-102">Procedimiento para establecer el valor que muestra el control ProgressBar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4b81-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="e4b81-103">El control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>; sin embargo, el control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="e4b81-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e4b81-104">El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] le ofrece varias formas de mostrar un valor determinado en el <xref:System.Windows.Forms.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="e4b81-104">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="e4b81-105">Método que elija dependerá de la tarea en cuestión o el problema que va a resolver.</span><span class="sxs-lookup"><span data-stu-id="e4b81-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="e4b81-106">La siguiente tabla muestra los enfoques que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="e4b81-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="e4b81-107">Enfoque</span><span class="sxs-lookup"><span data-stu-id="e4b81-107">Approach</span></span>|<span data-ttu-id="e4b81-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4b81-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e4b81-109">Establezca el valor de la <xref:System.Windows.Forms.ProgressBar> controlar directamente.</span><span class="sxs-lookup"><span data-stu-id="e4b81-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="e4b81-110">Este enfoque es útil para tareas donde se sabe el total del elemento medido que va a participar, como la lectura de registros desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e4b81-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="e4b81-111">Además, si solo tiene que establecer el valor de una o dos veces, esto es una manera fácil de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e4b81-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="e4b81-112">Por último, use este proceso si tiene que disminuya el valor mostrado por la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="e4b81-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="e4b81-113">Aumentar el <xref:System.Windows.Forms.ProgressBar> mostrar mediante un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="e4b81-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="e4b81-114">Este enfoque es útil cuando se va a mostrar un recuento simple entre los valores mínimo y máximo, por ejemplo, tiempo transcurrido o el número de archivos que se han procesado de un total conocido.</span><span class="sxs-lookup"><span data-stu-id="e4b81-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="e4b81-115">Aumentar el <xref:System.Windows.Forms.ProgressBar> mostrar en un valor variable.</span><span class="sxs-lookup"><span data-stu-id="e4b81-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="e4b81-116">Este enfoque es útil cuando necesita cambiar el valor mostrado un número de veces en cantidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="e4b81-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="e4b81-117">Un ejemplo podría mostrar la cantidad de espacio en disco consumido al escribir una serie de archivos en el disco.</span><span class="sxs-lookup"><span data-stu-id="e4b81-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="e4b81-118">La forma más directa para establecer el valor que se muestra una barra de progreso está estableciendo el <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4b81-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="e4b81-119">Esto puede hacerse en tiempo de diseño o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e4b81-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="e4b81-120">Para establecer el valor de ProgressBar directamente</span><span class="sxs-lookup"><span data-stu-id="e4b81-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="e4b81-121">Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.</span><span class="sxs-lookup"><span data-stu-id="e4b81-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="e4b81-122">En el código, establezca el control <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad en un valor entero entre los valores mínimos y máximo que ha establecido.</span><span class="sxs-lookup"><span data-stu-id="e4b81-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4b81-123">Si establece la <xref:System.Windows.Forms.ProgressBar.Value%2A> propiedad fuera de los límites establecidos por el <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> propiedades, el control genera un <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e4b81-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="e4b81-124">En el ejemplo de código siguiente se muestra cómo establecer el <xref:System.Windows.Forms.ProgressBar> valor directamente.</span><span class="sxs-lookup"><span data-stu-id="e4b81-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="e4b81-125">El código lee los registros de un origen de datos y la barra de progreso y la etiqueta actualiza cada vez que se lee un registro de datos.</span><span class="sxs-lookup"><span data-stu-id="e4b81-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="e4b81-126">Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> (control), un <xref:System.Windows.Forms.ProgressBar> control y una tabla de datos con una fila denominada `CustomerRow` con `FirstName` y `LastName` campos.</span><span class="sxs-lookup"><span data-stu-id="e4b81-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     Si desea mostrar el progreso que se realiza en un intervalo fijo, puede establecer el valor y, a continuación, llame al método que aumenta la <xref:System.Windows.Forms.ProgressBar> valor del control en ese intervalo. <span data-ttu-id="e4b81-128">Esto es útil para los temporizadores y otros escenarios donde no se mide el progreso como un porcentaje del total.</span><span class="sxs-lookup"><span data-stu-id="e4b81-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="e4b81-129">Para aumentar la barra de progreso en un valor fijo</span><span class="sxs-lookup"><span data-stu-id="e4b81-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="e4b81-130">Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.</span><span class="sxs-lookup"><span data-stu-id="e4b81-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="e4b81-131">Establecer el control <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad en un entero que representa la cantidad para aumentar la barra de progreso muestra el valor.</span><span class="sxs-lookup"><span data-stu-id="e4b81-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="e4b81-132">Llame a la <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> método para cambiar el valor mostrado por el número establecido en el <xref:System.Windows.Forms.ProgressBar.Step%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4b81-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="e4b81-133">En el ejemplo de código siguiente se muestra cómo una barra de progreso puede mantener un recuento de los archivos en una operación de copia.</span><span class="sxs-lookup"><span data-stu-id="e4b81-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="e4b81-134">En el ejemplo siguiente, tal como se lee cada archivo en la memoria, la barra de progreso y la etiqueta se actualizan para reflejar que el total de archivos de lectura.</span><span class="sxs-lookup"><span data-stu-id="e4b81-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="e4b81-135">Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="e4b81-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     Por último, puede aumentar el valor mostrado por una barra de progreso para que cada aumento es una cantidad única. <span data-ttu-id="e4b81-137">Esto es útil cuando se mantiene un seguimiento de una serie de operaciones únicas, como escribir archivos de distinto tamaño en un disco duro o medir el progreso como un porcentaje del total.</span><span class="sxs-lookup"><span data-stu-id="e4b81-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="e4b81-138">Para aumentar la barra de progreso en un valor dinámico</span><span class="sxs-lookup"><span data-stu-id="e4b81-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="e4b81-139">Establecer el <xref:System.Windows.Forms.ProgressBar> del control <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> valores.</span><span class="sxs-lookup"><span data-stu-id="e4b81-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="e4b81-140">Llame a la <xref:System.Windows.Forms.ProgressBar.Increment%2A> método para cambiar el valor mostrado por un número entero que especifique.</span><span class="sxs-lookup"><span data-stu-id="e4b81-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="e4b81-141">El ejemplo de código siguiente muestra cómo una barra de progreso puede calcular cuánto espacio en disco se ha utilizado durante una operación de copia.</span><span class="sxs-lookup"><span data-stu-id="e4b81-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="e4b81-142">En el ejemplo siguiente, tal como se escribe cada archivo en el disco duro, la barra de progreso y la etiqueta se actualizan para reflejar la cantidad de espacio en disco disponible.</span><span class="sxs-lookup"><span data-stu-id="e4b81-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="e4b81-143">Este ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="e4b81-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4b81-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4b81-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="e4b81-145">Información general sobre ProgressBar (Control)</span><span class="sxs-lookup"><span data-stu-id="e4b81-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="e4b81-146">ProgressBar (control)</span><span class="sxs-lookup"><span data-stu-id="e4b81-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
