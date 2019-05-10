---
title: Instrucciones de firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 06e5ba64ab0ec3558e4c773c9cb21f961384e0c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650038"
---
# <a name="firewall-instructions"></a><span data-ttu-id="e1251-102">Instrucciones de firewall</span><span class="sxs-lookup"><span data-stu-id="e1251-102">Firewall Instructions</span></span>
<span data-ttu-id="e1251-103">Debe habilitar varios puertos o programas en el firewall para que pueden funcionar los ejemplos de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e1251-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="e1251-104">Muchos de los ejemplos se comunican utilizando los puertos del intervalo 8000-8003 y el puerto 9000.</span><span class="sxs-lookup"><span data-stu-id="e1251-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="e1251-105">El firewall se activa de forma predeterminada y evita el acceso a estos puertos.</span><span class="sxs-lookup"><span data-stu-id="e1251-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="e1251-106">Para habilitar el firewall para los ejemplos, complete uno de los procedimientos siguientes, dependiendo de sus requisitos y entorno de seguridad:</span><span class="sxs-lookup"><span data-stu-id="e1251-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
- <span data-ttu-id="e1251-107">Opción 1: Habilite los ejemplos mientras se ejecutan de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="e1251-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="e1251-108">No realice ningún cambio de antemano en su configuración del firewall y proceda a iniciar la compilación y la ejecución de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e1251-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="e1251-109">Cuando se ejecuta un ejemplo, un **alerta de seguridad de Windows** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e1251-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="e1251-110">El programa de ejemplo en cuestión se puede agregar a continuación a una lista desbloqueada de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="e1251-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="e1251-111">Con este procedimiento, quizá tenga que reiniciar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1251-111">With this procedure, you may have to then restart the sample.</span></span>  
  
- <span data-ttu-id="e1251-112">Opción 2: Habilite de antemano los programas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1251-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="e1251-113">Iniciar el **Panel de Control de Firewall de Windows** subprograma y habilitar los programas de ejemplo que piensa ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e1251-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="e1251-114">Debe compilar primero los programas para que existan los archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="e1251-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="e1251-115">Encontrará instrucciones más detalladas en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1251-115">You can find more detailed instructions in the following procedure.</span></span>  
  
- <span data-ttu-id="e1251-116">Opción 3: Habilite de antemano un intervalo de puertos.</span><span class="sxs-lookup"><span data-stu-id="e1251-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="e1251-117">Iniciar el **Windows Firewall** **Panel de Control** applet y habilite los puertos 80, 443, 8000-8003 y 9000, que son utilizadas por los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e1251-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="e1251-118">Encontrará instrucciones más detalladas en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1251-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="e1251-119">Esta opción es menos segura que las otras porque permite que cualquier programa utilice estos puertos, no solamente los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e1251-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="e1251-120">Si no está seguro de qué procedimiento utilizar, elija la primera opción.</span><span class="sxs-lookup"><span data-stu-id="e1251-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="e1251-121">Si está ejecutando un firewall procedente de otro proveedor, quizá necesite realizar modificaciones similares.</span><span class="sxs-lookup"><span data-stu-id="e1251-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1251-122">Cambiar su configuración del firewall afecta a su seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1251-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="e1251-123">Se recomienda que grabe los cambios que efectúa y los quite cuando termine de trabajar con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e1251-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="e1251-124">Para habilitar de antemano los programas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1251-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="e1251-125">Compilar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e1251-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="e1251-126">Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="e1251-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="e1251-127">Se abrirá el **Panel de Control de Firewall de Windows** applet.</span><span class="sxs-lookup"><span data-stu-id="e1251-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1251-128">Debe tener permiso para cambiar los valores del Firewall para ejecutar los ejemplos que requieren la capacidad de comunicarse a través de Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1251-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="e1251-129">Si algunas configuraciones de firewall no están disponibles y su equipo está conectado a un dominio, el administrador del sistema podría estar controlando estos valores a través de Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="e1251-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="e1251-130">Complete uno de los siguientes pasos concretos para permitir que un programa pase a través del Firewall de Windows:</span><span class="sxs-lookup"><span data-stu-id="e1251-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    - <span data-ttu-id="e1251-131">En Windows 7 o Windows Server 2008 r2, haga clic en **permitir un programa o una característica a través de Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="e1251-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="e1251-132">Haga clic en **cambiar la configuración de**, permitir **otro programa...** .</span><span class="sxs-lookup"><span data-stu-id="e1251-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    - <span data-ttu-id="e1251-133">En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], haga clic en **permitir un programa a través de Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="e1251-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="e1251-134">En el **excepciones** , haga clic **Agregar programa**.</span><span class="sxs-lookup"><span data-stu-id="e1251-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="e1251-135">Haga clic en el **examinar** botón y seleccione el archivo ejecutable del ejemplo que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e1251-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="e1251-136">Repita los pasos 4 y 5 hasta que haya agregado los archivos ejecutables de todas las muestras que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e1251-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="e1251-137">Haga clic en **Aceptar** para cerrar el applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="e1251-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="e1251-138">Para habilitar de antemano un intervalo de puertos</span><span class="sxs-lookup"><span data-stu-id="e1251-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="e1251-139">Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="e1251-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="e1251-140">Se abrirá el **Panel de Control de Firewall de Windows** applet.</span><span class="sxs-lookup"><span data-stu-id="e1251-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="e1251-141">En Windows 7 o Windows Server 2008 R2, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e1251-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1. <span data-ttu-id="e1251-142">Haga clic en **configuración avanzada** en la columna izquierda de la ventana de Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1251-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2. <span data-ttu-id="e1251-143">Haga clic en **reglas de entrada** en la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="e1251-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3. <span data-ttu-id="e1251-144">Haga clic en **nuevas reglas** en la columna derecha.</span><span class="sxs-lookup"><span data-stu-id="e1251-144">Click **New Rules** in the right column.</span></span>  
  
    4. <span data-ttu-id="e1251-145">Seleccione **puerto** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1251-145">Select **Port** and click **next**.</span></span>  
  
    5. <span data-ttu-id="e1251-146">Seleccione **TCP** y escriba `8000, 8001, 8002, 8003, 9000, 80, 443` en el **puertos locales específicos** campo.</span><span class="sxs-lookup"><span data-stu-id="e1251-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6. <span data-ttu-id="e1251-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1251-147">Click **Next**.</span></span>  
  
    7. <span data-ttu-id="e1251-148">Seleccione **permitir la conexión**y haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="e1251-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8. <span data-ttu-id="e1251-149">Seleccione **dominio** y **privada**y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1251-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="e1251-150">Denomine a esta regla `WCF-WF 4.0 Samples`y haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e1251-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="e1251-151">Haga clic en **reglas de salida** y repita los pasos c a h.</span><span class="sxs-lookup"><span data-stu-id="e1251-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="e1251-152">En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e1251-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1. <span data-ttu-id="e1251-153">Haga clic en **permitir un programa a través de Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="e1251-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2. <span data-ttu-id="e1251-154">En el **excepciones** , haga clic **agregar puerto**.</span><span class="sxs-lookup"><span data-stu-id="e1251-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3. <span data-ttu-id="e1251-155">Escriba un nombre, escriba 8000 como el número de puerto y seleccione el **TCP** opción.</span><span class="sxs-lookup"><span data-stu-id="e1251-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4. <span data-ttu-id="e1251-156">Haga clic en el **Cambiar ámbito** botón, seleccione el **mi red** opción única (subred) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e1251-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5. <span data-ttu-id="e1251-157">Repita los pasos b a d con los puertos 8001, 8002, 8003, 9000, 80 y 443.</span><span class="sxs-lookup"><span data-stu-id="e1251-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="e1251-158">Haga clic en **Aceptar** para cerrar el applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="e1251-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1251-159">Quite cualquier excepción de firewall cuando acabe de trabajar con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e1251-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="e1251-160">Para ello, abra el **Panel de Control de Firewall de Windows** applet y quite cualquier programa o puerto entradas que se agregaron mediante los procedimientos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e1251-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
