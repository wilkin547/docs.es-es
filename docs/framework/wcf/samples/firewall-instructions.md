---
title: Instrucciones de firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 343fa695039f6767f6ab33daa4e3cc51e8db5e47
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899643"
---
# <a name="firewall-instructions"></a><span data-ttu-id="74bdf-102">Instrucciones de Firewall</span><span class="sxs-lookup"><span data-stu-id="74bdf-102">Firewall instructions</span></span>

<span data-ttu-id="74bdf-103">Debe habilitar varios puertos o programas en el firewall para que los ejemplos de Windows Communication Foundation (WCF) funcionen.</span><span class="sxs-lookup"><span data-stu-id="74bdf-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="74bdf-104">Muchos de los ejemplos se comunican utilizando los puertos del intervalo 8000-8003 y el puerto 9000.</span><span class="sxs-lookup"><span data-stu-id="74bdf-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="74bdf-105">El firewall se activa de forma predeterminada y evita el acceso a estos puertos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="74bdf-106">Para habilitar el firewall para los ejemplos, complete uno de los procedimientos siguientes, dependiendo de sus requisitos y entorno de seguridad:</span><span class="sxs-lookup"><span data-stu-id="74bdf-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>

- <span data-ttu-id="74bdf-107">Opción 1: Habilite de forma interactiva los ejemplos mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="74bdf-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="74bdf-108">No realice ningún cambio de antemano en su configuración del firewall y proceda a iniciar la compilación y la ejecución de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="74bdf-109">Cuando se ejecuta un ejemplo, aparece un cuadro de diálogo **alerta de seguridad de Windows** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="74bdf-110">El programa de ejemplo en cuestión se puede agregar a continuación a una lista desbloqueada de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="74bdf-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="74bdf-111">Con este procedimiento, quizá tenga que reiniciar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74bdf-111">With this procedure, you may have to then restart the sample.</span></span>

- <span data-ttu-id="74bdf-112">Opción 2: Habilite de antemano los programas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74bdf-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="74bdf-113">Inicie el applet **Panel de control de Firewall de Windows** y habilite los programas de ejemplo que piensa ejecutar.</span><span class="sxs-lookup"><span data-stu-id="74bdf-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="74bdf-114">Debe compilar primero los programas para que existan los archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="74bdf-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="74bdf-115">Encontrará instrucciones más detalladas en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="74bdf-115">You can find more detailed instructions in the following procedure.</span></span>

- <span data-ttu-id="74bdf-116">Opción 3: Habilite de antemano un intervalo del puerto.</span><span class="sxs-lookup"><span data-stu-id="74bdf-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="74bdf-117">Inicie el applet **Panel de control del firewall de Windows** y habilite los puertos 80, 443, 8000-8003 y 9000, que se usan en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-117">Start the **Windows Firewall Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="74bdf-118">Encontrará instrucciones más detalladas en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="74bdf-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="74bdf-119">Esta opción es menos segura que las otras porque permite que cualquier programa utilice estos puertos, no solamente los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>

<span data-ttu-id="74bdf-120">Si no está seguro de qué procedimiento utilizar, elija la primera opción.</span><span class="sxs-lookup"><span data-stu-id="74bdf-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="74bdf-121">Si está ejecutando un firewall procedente de otro proveedor, quizá necesite realizar modificaciones similares.</span><span class="sxs-lookup"><span data-stu-id="74bdf-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74bdf-122">Cambiar su configuración del firewall afecta a su seguridad.</span><span class="sxs-lookup"><span data-stu-id="74bdf-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="74bdf-123">Se recomienda que grabe los cambios que efectúa y los quite cuando termine de trabajar con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>

## <a name="enable-samples-programs-in-advance"></a><span data-ttu-id="74bdf-124">Habilitar programas de ejemplo de antemano</span><span class="sxs-lookup"><span data-stu-id="74bdf-124">Enable samples programs in advance</span></span>

1. <span data-ttu-id="74bdf-125">Cree el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74bdf-125">Build the sample.</span></span>

2. <span data-ttu-id="74bdf-126">Elija **inicio** > **ejecutar**y escriba `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="74bdf-126">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="74bdf-127">Se abrirá el applet **Panel de control del firewall de Windows** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-127">This opens the **Windows Firewall Control Panel** applet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74bdf-128">Debe tener permiso para cambiar los valores del Firewall para ejecutar los ejemplos que requieren la capacidad de comunicarse a través de Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="74bdf-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="74bdf-129">Si algunas configuraciones de firewall no están disponibles y su equipo está conectado a un dominio, el administrador del sistema podría estar controlando estos valores a través de Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="74bdf-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>

3. <span data-ttu-id="74bdf-130">Complete uno de los siguientes pasos específicos del funcionamiento para permitir un programa a través de Firewall de Windows:</span><span class="sxs-lookup"><span data-stu-id="74bdf-130">Complete one of the following operating-specific steps to allow a program through the Windows Firewall:</span></span>

    - <span data-ttu-id="74bdf-131">En Windows 7 o Windows Server 2008 R2, haga clic en **permitir un programa o una característica a través de Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-131">On Windows 7 or Windows Server 2008 R2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="74bdf-132">Haga clic en **Cambiar configuración** > **permitir otro programa**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-132">Click **Change Settings** > **Allow Another Program**.</span></span>

    - <span data-ttu-id="74bdf-133">En Windows Vista o Windows Server 2008, haga clic en **permitir un programa a través de Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-133">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>

4. <span data-ttu-id="74bdf-134">En la pestaña **excepciones** , haga clic en **Agregar programa**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-134">On the **Exceptions** tab, click **Add Program**.</span></span>

5. <span data-ttu-id="74bdf-135">Haga clic en el botón **examinar** y seleccione el archivo ejecutable del ejemplo que piensa ejecutar.</span><span class="sxs-lookup"><span data-stu-id="74bdf-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>

6. <span data-ttu-id="74bdf-136">Repita los pasos 4 y 5 hasta que haya agregado los archivos ejecutables de todos los ejemplos que piensa ejecutar.</span><span class="sxs-lookup"><span data-stu-id="74bdf-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>

7. <span data-ttu-id="74bdf-137">Haga clic en **Aceptar** para cerrar el applet de Firewall.</span><span class="sxs-lookup"><span data-stu-id="74bdf-137">Click **OK** to close the firewall applet.</span></span>

## <a name="enable-a-port-range-in-advance"></a><span data-ttu-id="74bdf-138">Habilitación de un intervalo de puertos de antemano</span><span class="sxs-lookup"><span data-stu-id="74bdf-138">Enable a port range in advance</span></span>

1. <span data-ttu-id="74bdf-139">Elija **inicio** > **ejecutar**y escriba `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="74bdf-139">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="74bdf-140">Se abrirá el applet **Panel de control del firewall de Windows** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-140">This opens the **Windows Firewall Control Panel** applet.</span></span>

2. <span data-ttu-id="74bdf-141">En Windows 7 o Windows Server 2008 R2, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>

    1. <span data-ttu-id="74bdf-142">Haga clic en **Configuración avanzada** en la columna izquierda de la ventana Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="74bdf-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>

    2. <span data-ttu-id="74bdf-143">Haga clic en **reglas de entrada** en la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="74bdf-143">Click **Inbound Rules** in the left column.</span></span>

    3. <span data-ttu-id="74bdf-144">Haga clic en **nuevas reglas** en la columna derecha.</span><span class="sxs-lookup"><span data-stu-id="74bdf-144">Click **New Rules** in the right column.</span></span>

    4. <span data-ttu-id="74bdf-145">Seleccione **Puerto** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-145">Select **Port** and click **next**.</span></span>

    5. <span data-ttu-id="74bdf-146">Seleccione **TCP** y escriba `8000, 8001, 8002, 8003, 9000, 80, 443` en el campo **puertos locales específicos** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>

    6. <span data-ttu-id="74bdf-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-147">Click **Next**.</span></span>

    7. <span data-ttu-id="74bdf-148">Seleccione **permitir la conexión**y haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-148">Select **Allow the connection**, and click **Next** .</span></span>

    8. <span data-ttu-id="74bdf-149">Seleccione **dominio** y **privado**y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-149">Select **Domain** and **Private**, and click **Next**.</span></span>

    9. <span data-ttu-id="74bdf-150">Asigne a esta regla el nombre `WCF-WF 4.0 Samples`y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>

    10. <span data-ttu-id="74bdf-151">Haga clic en **reglas de salida** y repita los pasos de c a h.</span><span class="sxs-lookup"><span data-stu-id="74bdf-151">Click **Outbound Rules** and repeat steps c to h.</span></span>

3. <span data-ttu-id="74bdf-152">En Windows Vista o Windows Server 2008, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-152">On Windows Vista or Windows Server 2008, follow these steps.</span></span>

    1. <span data-ttu-id="74bdf-153">Haga clic en **Permitir un programa a través del Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-153">Click **Allow a program through Windows Firewall**.</span></span>

    2. <span data-ttu-id="74bdf-154">En la pestaña **excepciones** , haga clic en **Agregar puerto**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-154">On the **Exceptions** tab, click **Add Port**.</span></span>

    3. <span data-ttu-id="74bdf-155">Escriba un nombre, escriba 8000 como número de puerto y seleccione la opción **TCP** .</span><span class="sxs-lookup"><span data-stu-id="74bdf-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>

    4. <span data-ttu-id="74bdf-156">Haga clic en el botón **cambiar ámbito** , seleccione la opción sólo **mi red** (subred) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="74bdf-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>

    5. <span data-ttu-id="74bdf-157">Repita los pasos b a d con los puertos 8001, 8002, 8003, 9000, 80 y 443.</span><span class="sxs-lookup"><span data-stu-id="74bdf-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>

4. <span data-ttu-id="74bdf-158">Haga clic en **Aceptar** para cerrar el applet de Firewall.</span><span class="sxs-lookup"><span data-stu-id="74bdf-158">Click **OK** to close the firewall applet.</span></span>

> [!NOTE]
> <span data-ttu-id="74bdf-159">Quite cualquier excepción de firewall cuando acabe de trabajar con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="74bdf-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="74bdf-160">Para ello, abra el applet del **Panel de control de Firewall de Windows** y quite los programas o entradas de puerto que se agregaron en los procedimientos anteriores.</span><span class="sxs-lookup"><span data-stu-id="74bdf-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
