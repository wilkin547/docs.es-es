---
title: "Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero.La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First.La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.  
  
> [!NOTE]
>  Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero.[!INCLUDE[crabout](../../../includes/crabout-md.md)] el desarrollo de servicio de flujo de trabajo de contrato primero, vea [Desarrollo de servicio de flujo de trabajo de contrato primero](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md).  
  
### Crear el proyecto de flujo de trabajo  
  
1.  En [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], seleccione **Archivo**, **Nuevo proyecto**.Seleccione el nodo **WCF** del nodo **C\#** en el árbol **Plantillas** y seleccione la plantilla **Aplicación de servicio de flujo de trabajo WCF**.  
  
2.  Asigne al nuevo proyecto el nombre `ContractFirst` y haga clic en **Aceptar**.  
  
### Crear el contrato de servicio  
  
1.  Haga clic con el botón secundario en **Explorador de soluciones** y seleccione **Agregar**, **Nuevo elemento...**Seleccione el nodo **Código** de la izquierda y la plantilla **Clase** de la derecha.Asigne a la nueva clase el nombre `IBookService` y haga clic en **Aceptar**.  
  
2.  En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  Compile el proyecto; para ello, presione **Ctrl\+Mayús\+B**.  
  
### Importar el contrato de servicio  
  
1.  Haga clic con el botón secundario en el proyecto en **Explorador de soluciones** y seleccione **Importar contrato de servicio**.En **\<Proyecto actual\>**, abra todos los subnodos y seleccione **IBookService**.Haga clic en **Aceptar**.  
  
2.  Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto.Haga clic en **Aceptar**.  
  
3.  Compile el proyecto; para ello, presione **Ctrl\+Mayús\+B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.  
  
4.  En el **Explorador de soluciones**, abra Service1.xamlx.El servicio de flujo de trabajo aparecerá en el diseñador.  
  
5.  Seleccione la actividad **Sequence**.En la ventana Propiedades, haga clic en el botón **...** de la propiedad **ImplementedContract**.En la ventana **Editor de colecciones de tipos** que aparece, haga clic en la lista desplegable **Tipo** y seleccione la entrada **Buscar tipos…**En el cuadro de diálogo **Examinar y seleccionar un tipo .NET**, en **\<Proyecto actual\>**, abra todos los subnodos y seleccione **IBookService**.Haga clic en **Aceptar**.En el cuadro de diálogo **Editor de colecciones de tipos**, haga clic en **Aceptar**.  
  
6.  Seleccione y elimine las actividades **ReceiveRequest** y **SendResponse**.  
  
7.  En el cuadro de herramientas, arrastre una actividad **Buy\_ReceiveAndSendReply** y **Checkout\_Receive** sobre la actividad **Sequential Service**.