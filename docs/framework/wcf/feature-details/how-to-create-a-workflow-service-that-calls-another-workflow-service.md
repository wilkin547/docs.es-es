---
title: Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0a3b9f77445e8629fb67d099c6d7944044897fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="6be0d-102">Crear un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6be0d-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="6be0d-103">A veces es necesario que un servicio de flujo de trabajo obtenga información de otro servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6be0d-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="6be0d-104">En este tema se muestra cómo llamar a un servicio de flujo de trabajo desde otro.</span><span class="sxs-lookup"><span data-stu-id="6be0d-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="6be0d-105">En este tema, crearemos dos servicios de flujo de trabajo; uno que tiene un método que invierte la cadena de entrada y otro que convierte la cadena de entrada en letras mayúsculas después de invertir la cadena que utiliza el primer servicio.</span><span class="sxs-lookup"><span data-stu-id="6be0d-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="6be0d-106">Crear el servicio de flujo de trabajo Reverser</span><span class="sxs-lookup"><span data-stu-id="6be0d-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="6be0d-107">Ejecute [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] como administrador.</span><span class="sxs-lookup"><span data-stu-id="6be0d-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="6be0d-108">Seleccione **archivo**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="6be0d-109">En el **flujo de trabajo** nodo en el **plantillas instaladas** panel, seleccione **aplicación de servicio de flujo de trabajo de WCF**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="6be0d-110">Llame a la solución `NestedServices` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="6be0d-111">En **servidores**, asegúrese de que **usar servidor Web de IIS Local** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6be0d-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="6be0d-112">Haga clic en **crear un directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="6be0d-113">Haga clic en **Aceptar** en el cuadro de diálogo que indica que el directorio virtual se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6be0d-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="6be0d-114">En el Explorador de soluciones, cambie el nombre de Service1.xamlx a `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="6be0d-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="6be0d-115">En el **propiedades del proyecto** página para el nuevo proyecto, haga clic en el **Web** ficha. Establecer el **acción de inicio** a **página específica**y seleccione StringReverserService.xamlx como la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="6be0d-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="6be0d-116">Abra StringReverserService.xamlx en el diseñador y elimine las actividades `ReceiveRequest` y `SendReply` existentes, y a continuación arrastre una actividad `ReceiveAndSendReply` a la actividad de secuencia existente.</span><span class="sxs-lookup"><span data-stu-id="6be0d-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="6be0d-117">Establecer el **OperationName** en ReverseString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="6be0d-118">Establecer el **ServiceContractName** en IReverseString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="6be0d-119">Seleccione el **CanCreateInstance** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="6be0d-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="6be0d-120">Seleccione el **SequentialService** actividad y, a continuación, haga clic en el **Variables** ficha en la parte inferior del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6be0d-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="6be0d-121">Cree dos nuevas variables denominadas que StringToReverse y ReversedStringToReturn de tipo String.</span><span class="sxs-lookup"><span data-stu-id="6be0d-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="6be0d-122">Haga clic en el **definir** vincular en el **recepción** actividad.</span><span class="sxs-lookup"><span data-stu-id="6be0d-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="6be0d-123">Haga clic en el **parámetros**y cree un parámetro denominado InputString de tipo String que se asigne a StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="6be0d-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="6be0d-124">Haga clic en el **definir** vincular en el **SendReplyToReceive** actividad.</span><span class="sxs-lookup"><span data-stu-id="6be0d-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="6be0d-125">Haga clic en el **parámetros**y cree un parámetro denominado ReversedString del tipo String, asignado a ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="6be0d-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="6be0d-126">Para implementar la lógica para el servicio, cree en el proyecto una nueva clase llamada StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="6be0d-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="6be0d-127">Reemplace la definición de clase por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6be0d-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="6be0d-128">Para llamar al método ReverseString en la entrada, arrastre un **InvokeMethod** actividad en el cuadro de herramientas hasta el espacio entre el **recepción** y **SendReply** actividades.</span><span class="sxs-lookup"><span data-stu-id="6be0d-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="6be0d-129">Establezca las propiedades de la actividad de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="6be0d-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="6be0d-130">**MethodName**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="6be0d-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="6be0d-131">**Resultado**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="6be0d-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="6be0d-132">**Parámetros de**: crear un nuevo parámetro con un **dirección** de In, un **tipo** de cadena y un **valor** de StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="6be0d-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="6be0d-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="6be0d-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="6be0d-134">Compruebe el servicio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="6be0d-134">Test the service by pressing F5.</span></span> <span data-ttu-id="6be0d-135">En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString().</span><span class="sxs-lookup"><span data-stu-id="6be0d-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="6be0d-136">En el panel de la solicitud, escriba `Sample` para el valor del parámetro InputString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="6be0d-137">Haga clic en **invocar**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-137">Click **Invoke**.</span></span> <span data-ttu-id="6be0d-138">El servicio debería devolver "elpmaS".</span><span class="sxs-lookup"><span data-stu-id="6be0d-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="6be0d-139">Crear el servicio de flujo de trabajo UpperCaser</span><span class="sxs-lookup"><span data-stu-id="6be0d-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="6be0d-140">Haga clic en el proyecto NestedServices y seleccione **agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="6be0d-141">En el **flujo de trabajo** nodo, seleccione **servicio de flujo de trabajo de WCF**y el nombre del nuevo servicio `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="6be0d-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="6be0d-142">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-142">Click **Add**.</span></span> <span data-ttu-id="6be0d-143">Esto debería agregar al proyecto un nuevo servicio de flujo de trabajo llamado UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6be0d-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="6be0d-144">Abra UpperCaserService.xamlx en el diseñador y elimine las existentes **ReceiveRequest** y `SendReply` actividades y arrastre un `ReceiveAndSendReply` actividad a la actividad de secuencia existente.</span><span class="sxs-lookup"><span data-stu-id="6be0d-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="6be0d-145">Establecer el **OperationName** en UpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="6be0d-146">Establecer el **ServiceContractName** en IUpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="6be0d-147">Seleccione el **CanCreateInstance** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="6be0d-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="6be0d-148">Seleccione la actividad SequentialService y, a continuación, haga clic en el **Variables** ficha en la parte inferior del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6be0d-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="6be0d-149">Cree tres nuevas variables denominadas que StringToUpper, StringToReverse y StringToReturn de tipo String.</span><span class="sxs-lookup"><span data-stu-id="6be0d-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="6be0d-150">Haga clic en el **definir** vincular en el **recepción** actividad.</span><span class="sxs-lookup"><span data-stu-id="6be0d-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="6be0d-151">Haga clic en el **parámetros**y cree un parámetro denominado InputString de tipo String que se asigne a StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="6be0d-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="6be0d-152">Haga clic en el **definir** vincular en el **SendReplyToReceive** actividad.</span><span class="sxs-lookup"><span data-stu-id="6be0d-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="6be0d-153">Haga clic en el **parámetros**y cree un parámetro denominado ModifiedString del tipo String, asignado a StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="6be0d-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="6be0d-154">Para implementar la lógica para el servicio, cree un nuevo método en la clase StringLibrary utilizando el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="6be0d-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="6be0d-155">Para llamar al método UpperCaseString en la entrada, arrastre un **InvokeMethod** actividad en el cuadro de herramientas hasta el espacio entre el **recepción** y **SendReply** actividades.</span><span class="sxs-lookup"><span data-stu-id="6be0d-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="6be0d-156">Establezca las propiedades de la actividad de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="6be0d-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="6be0d-157">**MethodName**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="6be0d-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="6be0d-158">**Resultado**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="6be0d-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="6be0d-159">**Parámetros de**: crear un nuevo parámetro con un **dirección** de In, un **tipo** de cadena y un **valor** de StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="6be0d-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="6be0d-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="6be0d-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="6be0d-161">Llamaremos ahora al primer servicio en la cadena modificada.</span><span class="sxs-lookup"><span data-stu-id="6be0d-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="6be0d-162">Haga clic en el proyecto y seleccione **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="6be0d-163">Agregue una referencia de servicio al servicio enhttp://localhost/NestedServices/StringReverserService.xamlx y compile el proyecto para crear una actividad personalizada para tener acceso al primer servicio web.</span><span class="sxs-lookup"><span data-stu-id="6be0d-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="6be0d-164">Arrastre una instancia de la nueva actividad en el flujo de trabajo, entre el **InvokeMethod** actividad y el **SendReplyToReceive** actividades.</span><span class="sxs-lookup"><span data-stu-id="6be0d-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="6be0d-165">Asigne la variable StringToReverse a la propiedad InputString de la nueva actividad y la variable StringToReturn a la propiedad StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="6be0d-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="6be0d-166">Abra la página de propiedades para el proyecto NestedServices y cambie el **página específica** en el **Web** ficha a UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6be0d-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="6be0d-167">Compruebe el servicio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="6be0d-167">Test the service by pressing F5.</span></span> <span data-ttu-id="6be0d-168">En el Cliente de prueba WCF que aparece, haga doble clic en el método ReverseString().</span><span class="sxs-lookup"><span data-stu-id="6be0d-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="6be0d-169">En el panel de la solicitud, escriba `Sample` para el valor del parámetro InputString.</span><span class="sxs-lookup"><span data-stu-id="6be0d-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="6be0d-170">Haga clic en **invocar**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-170">Click **Invoke**.</span></span> <span data-ttu-id="6be0d-171">El servicio debería devolver "ELPMAS".</span><span class="sxs-lookup"><span data-stu-id="6be0d-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="6be0d-172">Crear un cliente para que llame al servicio</span><span class="sxs-lookup"><span data-stu-id="6be0d-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="6be0d-173">Agregue un nuevo proyecto de aplicación de consola llamado Cliente a la solución.</span><span class="sxs-lookup"><span data-stu-id="6be0d-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="6be0d-174">Haga clic en el proyecto de cliente y seleccione **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="6be0d-175">En la ventana que aparece, haga clic en **Discover**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="6be0d-176">Seleccione StringReverserService.xamlx y escriba ReverseService como el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6be0d-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="6be0d-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6be0d-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="6be0d-178">Reemplace el método Main en Program.cs con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="6be0d-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
