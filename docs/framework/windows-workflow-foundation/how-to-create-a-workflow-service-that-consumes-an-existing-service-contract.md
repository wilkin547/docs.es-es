---
title: Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 6d7fa8c9faa84efc84243387cd27aa264f6155eb
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989622"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
.NET Framework 4,5 ofrece una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero. La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First. La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.  
  
> [!NOTE]
> Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero. Para obtener más información sobre el desarrollo de servicios de flujo de trabajo de contrato primero, vea [contrato primer desarrollo de servicio de flujo de trabajo](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Crear el proyecto de flujo de trabajo  
  
1. En Visual Studio, seleccione **archivo**, **nuevo proyecto**. Seleccione el nodo **WCF** en el **C#** nodo del árbol **plantillas** y seleccione la plantilla **aplicación de servicio de flujo de trabajo WCF** .  
  
2. Asigne un nombre al `ContractFirst` nuevo proyecto y haga clic en **Aceptar**.  
  
### <a name="creating-the-service-contract"></a>Crear el contrato de servicio  
  
1. Haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento.** ... Seleccione el nodo de **código** de la izquierda y la plantilla de **clase** a la derecha. Asigne a la nueva `IBookService` clase el nombre y haga clic en **Aceptar**.  
  
2. En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. Para compilar el proyecto, presione **Ctrl + Mayús + B**.  
  
### <a name="importing-the-service-contract"></a>Importar el contrato de servicio  
  
1. Haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **importar contrato de servicio**. **En\<> del proyecto actual**, Abra todos los subnodos y seleccione **IBookService**. Haga clic en **OK**.  
  
2. Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto. Haga clic en **OK**.  
  
3. Para compilar el proyecto, presione **Ctrl + Mayús + B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.  
  
4. En **Explorador de soluciones**, abra Service1. xamlx. El servicio de flujo de trabajo aparecerá en el diseñador.  
  
5. Seleccione la actividad **secuencia** . En el ventana Propiedades, haga clic en **...** en la propiedad **ImplementedContract** . En la ventana **Editor de colección de tipos** que aparece, haga clic en la lista desplegable **tipo** y seleccione el botón **Buscar tipos..** . movimientos. En el cuadro de diálogo **examinar y seleccionar un tipo .net** , en  **\<proyecto actual >** , Abra todos los subnodos y seleccione **IBookService**. Haga clic en **OK**. En el cuadro de diálogo **Editor de colección de tipos** , haga clic en **Aceptar**.  
  
6. Seleccione y elimine las actividades **ReceiveRequest** y **SendResponse** .  
  
7. En el cuadro de herramientas, arrastre una actividad **Buy_ReceiveAndSendReply** y **Checkout_Receive** a la actividad de **servicio secuencial** .
