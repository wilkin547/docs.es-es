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
# <a name="firewall-instructions"></a>Instrucciones de Firewall

Debe habilitar varios puertos o programas en el firewall para que los ejemplos de Windows Communication Foundation (WCF) funcionen. Muchos de los ejemplos se comunican utilizando los puertos del intervalo 8000-8003 y el puerto 9000. El firewall se activa de forma predeterminada y evita el acceso a estos puertos. Para habilitar el firewall para los ejemplos, complete uno de los procedimientos siguientes, dependiendo de sus requisitos y entorno de seguridad:

- Opción 1: Habilite de forma interactiva los ejemplos mientras se ejecutan. No realice ningún cambio de antemano en su configuración del firewall y proceda a iniciar la compilación y la ejecución de los ejemplos. Cuando se ejecuta un ejemplo, aparece un cuadro de diálogo **alerta de seguridad de Windows** . El programa de ejemplo en cuestión se puede agregar a continuación a una lista desbloqueada de forma interactiva. Con este procedimiento, quizá tenga que reiniciar el ejemplo.

- Opción 2: Habilite de antemano los programas de ejemplo. Inicie el applet **Panel de control de Firewall de Windows** y habilite los programas de ejemplo que piensa ejecutar. Debe compilar primero los programas para que existan los archivos ejecutables. Encontrará instrucciones más detalladas en el procedimiento siguiente.

- Opción 3: Habilite de antemano un intervalo del puerto. Inicie el applet **Panel de control del firewall de Windows** y habilite los puertos 80, 443, 8000-8003 y 9000, que se usan en los ejemplos. Encontrará instrucciones más detalladas en el procedimiento siguiente. Esta opción es menos segura que las otras porque permite que cualquier programa utilice estos puertos, no solamente los ejemplos.

Si no está seguro de qué procedimiento utilizar, elija la primera opción. Si está ejecutando un firewall procedente de otro proveedor, quizá necesite realizar modificaciones similares.

> [!IMPORTANT]
> Cambiar su configuración del firewall afecta a su seguridad. Se recomienda que grabe los cambios que efectúa y los quite cuando termine de trabajar con los ejemplos.

## <a name="enable-samples-programs-in-advance"></a>Habilitar programas de ejemplo de antemano

1. Cree el ejemplo.

2. Elija **inicio** > **ejecutar**y escriba `firewall.cpl`. Se abrirá el applet **Panel de control del firewall de Windows** .

    > [!NOTE]
    > Debe tener permiso para cambiar los valores del Firewall para ejecutar los ejemplos que requieren la capacidad de comunicarse a través de Firewall de Windows. Si algunas configuraciones de firewall no están disponibles y su equipo está conectado a un dominio, el administrador del sistema podría estar controlando estos valores a través de Directiva de grupo.

3. Complete uno de los siguientes pasos específicos del funcionamiento para permitir un programa a través de Firewall de Windows:

    - En Windows 7 o Windows Server 2008 R2, haga clic en **permitir un programa o una característica a través de Firewall de Windows**. Haga clic en **Cambiar configuración** > **permitir otro programa**.

    - En Windows Vista o Windows Server 2008, haga clic en **permitir un programa a través de Firewall de Windows**.

4. En la pestaña **excepciones** , haga clic en **Agregar programa**.

5. Haga clic en el botón **examinar** y seleccione el archivo ejecutable del ejemplo que piensa ejecutar.

6. Repita los pasos 4 y 5 hasta que haya agregado los archivos ejecutables de todos los ejemplos que piensa ejecutar.

7. Haga clic en **Aceptar** para cerrar el applet de Firewall.

## <a name="enable-a-port-range-in-advance"></a>Habilitación de un intervalo de puertos de antemano

1. Elija **inicio** > **ejecutar**y escriba `firewall.cpl`. Se abrirá el applet **Panel de control del firewall de Windows** .

2. En Windows 7 o Windows Server 2008 R2, siga estos pasos.

    1. Haga clic en **Configuración avanzada** en la columna izquierda de la ventana Firewall de Windows.

    2. Haga clic en **reglas de entrada** en la columna izquierda.

    3. Haga clic en **nuevas reglas** en la columna derecha.

    4. Seleccione **Puerto** y haga clic en **siguiente**.

    5. Seleccione **TCP** y escriba `8000, 8001, 8002, 8003, 9000, 80, 443` en el campo **puertos locales específicos** .

    6. Haga clic en **Siguiente**.

    7. Seleccione **permitir la conexión**y haga clic en **siguiente** .

    8. Seleccione **dominio** y **privado**y haga clic en **siguiente**.

    9. Asigne a esta regla el nombre `WCF-WF 4.0 Samples`y haga clic en **Finalizar**.

    10. Haga clic en **reglas de salida** y repita los pasos de c a h.

3. En Windows Vista o Windows Server 2008, siga estos pasos.

    1. Haga clic en **Permitir un programa a través del Firewall de Windows**.

    2. En la pestaña **excepciones** , haga clic en **Agregar puerto**.

    3. Escriba un nombre, escriba 8000 como número de puerto y seleccione la opción **TCP** .

    4. Haga clic en el botón **cambiar ámbito** , seleccione la opción sólo **mi red** (subred) y haga clic en **Aceptar**.

    5. Repita los pasos b a d con los puertos 8001, 8002, 8003, 9000, 80 y 443.

4. Haga clic en **Aceptar** para cerrar el applet de Firewall.

> [!NOTE]
> Quite cualquier excepción de firewall cuando acabe de trabajar con los ejemplos. Para ello, abra el applet del **Panel de control de Firewall de Windows** y quite los programas o entradas de puerto que se agregaron en los procedimientos anteriores.
