---
title: Instrucciones de firewall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
caps.latest.revision: "32"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0aac3a161b0482bad1a32f5223d2031402a632cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="firewall-instructions"></a>Instrucciones de firewall
Debe habilitar varios puertos o programas en el firewall para que los ejemplos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puedan funcionar. Muchos de los ejemplos se comunican utilizando los puertos del intervalo 8000-8003 y el puerto 9000. El firewall se activa de forma predeterminada y evita el acceso a estos puertos. Para habilitar el firewall para los ejemplos, complete uno de los procedimientos siguientes, dependiendo de sus requisitos y entorno de seguridad:  
  
-   Opción 1: Habilite de forma interactiva los ejemplos mientras se ejecutan. No realice ningún cambio de antemano en su configuración del firewall y proceda a iniciar la compilación y la ejecución de los ejemplos. Cuando se ejecuta un ejemplo, un **alerta de seguridad de Windows** aparece el cuadro de diálogo. El programa de ejemplo en cuestión se puede agregar a continuación a una lista desbloqueada de forma interactiva. Con este procedimiento, quizá tenga que reiniciar el ejemplo.  
  
-   Opción 2: Habilite de antemano los programas de ejemplo. Iniciar el **Panel de Control de Firewall de Windows** applet y habilitar los programas de ejemplo que piensa ejecutarse. Debe compilar primero los programas para que existan los archivos ejecutables. Encontrará instrucciones más detalladas en el procedimiento siguiente.  
  
-   Opción 3: Habilite de antemano un intervalo del puerto. Iniciar el **Firewall de Windows** **el Panel de Control** applet y habilite los puertos 80, 443, 8000-8003 y 9000, utilizados por los ejemplos. Encontrará instrucciones más detalladas en el procedimiento siguiente. Esta opción es menos segura que las otras porque permite que cualquier programa utilice estos puertos, no solamente los ejemplos.  
  
 Si no está seguro de qué procedimiento utilizar, elija la primera opción. Si está ejecutando un firewall procedente de otro proveedor, quizá necesite realizar modificaciones similares.  
  
> [!IMPORTANT]
>  Cambiar su configuración del firewall afecta a su seguridad. Se recomienda que grabe los cambios que efectúa y los quite cuando termine de trabajar con los ejemplos.  
  
### <a name="to-enable-samples-programs-in-advance"></a>Para habilitar de antemano los programas de ejemplo  
  
1.  Compilar el ejemplo.  
  
2.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo de `firewall.cpl`. Se abrirá la **Panel de Control de Firewall de Windows** applet.  
  
    > [!NOTE]
    >  Debe tener permiso para cambiar los valores del Firewall para ejecutar los ejemplos que requieren la capacidad de comunicarse a través de Firewall de Windows. Si algunas configuraciones de firewall no están disponibles y su equipo está conectado a un dominio, el administrador del sistema podría estar controlando estos valores a través de Directiva de grupo.  
  
3.  Complete uno de los siguientes pasos concretos para permitir que un programa pase a través del Firewall de Windows:  
  
    -   En Windows 7 o Windows Server 2008 r2, haga clic en **permitir un programa o una característica a través de Firewall de Windows**. Haga clic en **cambiar la configuración de**, permitir **otro programa...** .  
  
    -   En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], haga clic en **permitir un programa a través de Firewall de Windows**.  
  
4.  En el **excepciones** , haga clic en **Agregar programa**.  
  
5.  Haga clic en el **examinar** botón y seleccione el archivo ejecutable de ejemplo que piensa ejecutar.  
  
6.  Repita los pasos 4 y 5 hasta que haya agregado los archivos ejecutables de todas las muestras que se va a ejecutar.  
  
7.  Haga clic en **Aceptar** para cerrar el applet del firewall.  
  
### <a name="to-enable-a-port-range-in-advance"></a>Para habilitar de antemano un intervalo de puertos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo de `firewall.cpl`. Se abrirá la **Panel de Control de Firewall de Windows** applet.  
  
2.  En Windows 7 o Windows Server 2008 R2, siga estos pasos.  
  
    1.  Haga clic en **configuración avanzada** en la columna izquierda de la ventana de Firewall de Windows.  
  
    2.  Haga clic en **reglas de entrada** en la columna izquierda.  
  
    3.  Haga clic en **nuevas reglas** en la columna derecha.  
  
    4.  Seleccione **puerto** y haga clic en **siguiente**.  
  
    5.  Seleccione **TCP** y escriba `8000, 8001, 8002, 8003, 9000, 80, 443` en el **puertos locales específicos** campo.  
  
    6.  Haga clic en **Siguiente**.  
  
    7.  Seleccione **permitir la conexión**y haga clic en **siguiente** .  
  
    8.  Seleccione **dominio** y **privada**y haga clic en **siguiente**.  
  
    9. Denomine a esta regla `WCF-WF 4.0 Samples`y haga clic en **finalizar**.  
  
    10. Haga clic en **reglas de salida** y repita los pasos c a h.  
  
3.  En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], siga estos pasos.  
  
    1.  Haga clic en **permitir un programa a través de Firewall de Windows**.  
  
    2.  En el **excepciones** , haga clic en **agregar puerto**.  
  
    3.  Escriba un nombre, escriba 8000 como el número de puerto y seleccione el **TCP** opción.  
  
    4.  Haga clic en el **Cambiar ámbito** botón, seleccione la **mi red** opción única (subred) y haga clic en **Aceptar**.  
  
    5.  Repita los pasos b a d con los puertos 8001, 8002, 8003, 9000, 80 y 443.  
  
4.  Haga clic en **Aceptar** para cerrar el applet del firewall.  
  
> [!NOTE]
>  Quite cualquier excepción de firewall cuando acabe de trabajar con los ejemplos. Para ello, abra el **Panel de Control de Firewall de Windows** applet y quite cualquier programa o puerto entradas que se agregaron mediante los procedimientos anteriores.
