---
title: "Instrucciones de firewall | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
caps.latest.revision: 32
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 32
---
# Instrucciones de firewall
Debe habilitar varios puertos o programas en el firewall para que los ejemplos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puedan funcionar.Muchos de los ejemplos se comunican utilizando los puertos del intervalo 8000\-8003 y el puerto 9000.El firewall se activa de forma predeterminada y evita el acceso a estos puertos.Para habilitar el firewall para los ejemplos, complete uno de los procedimientos siguientes, dependiendo de sus requisitos y entorno de seguridad:  
  
-   Opción 1: Habilite de forma interactiva los ejemplos mientras se ejecutan.No realice ningún cambio de antemano en su configuración del firewall y proceda a iniciar la compilación y la ejecución de los ejemplos.Cuando se ejecuta un ejemplo, aparece un cuadro de diálogo **Alerta de seguridad de Windows**.El programa de ejemplo en cuestión se puede agregar a continuación a una lista desbloqueada de forma interactiva.Con este procedimiento, quizá tenga que reiniciar el ejemplo.  
  
-   Opción 2: Habilite de antemano los programas de ejemplo.Inicie el applet **Panel de control del firewall de Windows** y habilite los programas de ejemplo que piensa ejecutarse.Debe compilar primero los programas para que existan los archivos ejecutables.Encontrará instrucciones más detalladas en el procedimiento siguiente.  
  
-   Opción 3: Habilite de antemano un intervalo del puerto.Inicie el applet **Panel de control** del **firewall de Windows** y habilite los puertos 80, 443, 8000\-8003 y 9000, utilizados por los ejemplos.Encontrará instrucciones más detalladas en el procedimiento siguiente.Esta opción es menos segura que las otras porque permite que cualquier programa utilice estos puertos, no solamente los ejemplos.  
  
 Si no está seguro de qué procedimiento utilizar, elija la primera opción.Si está ejecutando un firewall procedente de otro proveedor, quizá necesite realizar modificaciones similares.  
  
> [!IMPORTANT]
>  Cambiar su configuración del firewall afecta a su seguridad.Se recomienda que grabe los cambios que efectúa y los quite cuando termine de trabajar con los ejemplos.  
  
### Para habilitar de antemano los programas de ejemplo  
  
1.  Compilar el ejemplo.  
  
2.  Haga clic en **Inicio**, haga clic en **Ejecutar** y escriba `firewall.cpl`.De esta forma se abre el applet **Panel de control del Firewall de Windows**.  
  
    > [!NOTE]
    >  Debe tener permiso para cambiar los valores del Firewall para ejecutar los ejemplos que requieren la capacidad de comunicarse a través de Firewall de Windows.Si algunas configuraciones de firewall no están disponibles y su equipo está conectado a un dominio, el administrador del sistema podría estar controlando estos valores a través de Directiva de grupo.  
  
3.  Complete uno de los siguientes pasos concretos para permitir que un programa pase a través del Firewall de Windows:  
  
    -   En Windows 7 o Windows Server 2008 R2, haga clic en **Permitir un programa o característica a través de Firewall de Windows**.Haga clic en **Cambiar configuración**, Permitir **otro programa...**.  
  
    -   En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], haga clic en **Permitir un programa a través del Firewall de Windows**.  
  
4.  En la pestaña **Excepciones**, haga clic en **Agregar programa**.  
  
5.  Haga clic en el botón **Examinar** y seleccione el archivo ejecutable del ejemplo que piensa ejecutar.  
  
6.  Repita los pasos 4 y 5 hasta que haya agregado los archivos ejecutables de todos los ejemplos que piensa ejecutar.  
  
7.  Haga clic en **Aceptar** para cerrar el applet del firewall.  
  
### Para habilitar de antemano un intervalo de puertos  
  
1.  Haga clic en **Inicio**, haga clic en **Ejecutar** y escriba `firewall.cpl`.De esta forma se abre el applet **Panel de control del Firewall de Windows**.  
  
2.  En Windows 7 o Windows Server 2008 R2, siga estos pasos.  
  
    1.  Haga clic en **Configuración avanzada** en la columna izquierda de la ventana de Firewall de Windows.  
  
    2.  Haga clic en **Reglas de entrada** en la columna de la izquierda.  
  
    3.  Haga clic en **Nuevas reglas** en la columna de la derecha.  
  
    4.  Seleccione **Puerto** y haga clic en **Siguiente**.  
  
    5.  Seleccione **TCP** y escriba `8000, 8001, 8002, 8003, 9000, 80, 443` en el campo **Puertos locales específicos**.  
  
    6.  Haga clic en **Siguiente**.  
  
    7.  Seleccione **Permitir la conexión** y haga clic en **Siguiente**.  
  
    8.  Seleccione **Dominio** y **Privado**, y haga clic en **Siguiente**.  
  
    9. Denomine a esta regla `Ejemplos de WCF WF 4.0` y haga clic en **Finalizar**.  
  
    10. Haga clic en **Reglas de salida** y repita los pasos c a h.  
  
3.  En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)], siga estos pasos.  
  
    1.  Haga clic en **Permitir un programa a través del Firewall de Windows**.  
  
    2.  En la pestaña **Excepciones**, haga clic en **Agregar puerto**.  
  
    3.  Escriba un nombre, escriba el número de puerto 8000 y seleccione la opción **TCP**.  
  
    4.  Haga clic en el botón **Cambiar ámbito**, seleccione la opción solo **Mi Red** \(subred\) y haga clic en **Aceptar**.  
  
    5.  Repita los pasos b a d con los puertos 8001, 8002, 8003, 9000, 80 y 443.  
  
4.  Haga clic en **Aceptar** para cerrar el applet del firewall.  
  
> [!NOTE]
>  Quite cualquier excepción de firewall cuando termine de trabajar con los ejemplos.Para hacerlo, abra el applet **Panel de control del firewall de Windows** y quite todas las entradas de programa o puerto agregadas por los procedimientos anteriores.