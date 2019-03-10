---
title: Filtrar Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 57babf216821665613da053f972ff25488418b7d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705069"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Filtrar Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero. La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First. La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.  
  
> [!NOTE]
>  Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero. Para obtener más información sobre el desarrollo de servicio de flujo de trabajo de contrato primero, consulte [desarrollo de servicio de flujo de trabajo de contrato primero](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Crear el proyecto de flujo de trabajo  
  
1.  En Visual Studio, seleccione **archivo**, **nuevo proyecto**. Seleccione el **WCF** nodo bajo el **C#** nodo en el **plantillas** del árbol y seleccione el **aplicación de servicio de flujo de trabajo de WCF** plantilla.  
  
2.  Asigne al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.  
  
### <a name="creating-the-service-contract"></a>Crear el contrato de servicio  
  
1.  Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** . Seleccione el **código** nodo a la izquierda y el **clase** plantilla a la derecha. Nombre de la nueva clase `IBookService` y haga clic en **Aceptar**.  
  
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
  
4.  Compile el proyecto presionando **Ctrl + Mayús + B**.  
  
### <a name="importing-the-service-contract"></a>Importar el contrato de servicio  
  
1.  Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **importar contrato de servicio**. En  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**. Haga clic en **Aceptar**.  
  
2.  Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto. Haga clic en **Aceptar**.  
  
3.  Compile el proyecto presionando **Ctrl + Mayús + B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.  
  
4.  En **el Explorador de soluciones**, abra Service1.xamlx. El servicio de flujo de trabajo aparecerá en el diseñador.  
  
5.  Seleccione el **secuencia** actividad. En la ventana Propiedades, haga clic en el **...** botón en el **ImplementedContract** propiedad. En el **Editor de la colección de tipo** ventana que aparece, haga clic en el **tipo** lista desplegable y seleccione el **buscar tipos...** entrada. En el **examinar y seleccionar .net tipo** cuadro de diálogo, en  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**. Haga clic en **Aceptar**. En el **Editor de la colección de tipo** cuadro de diálogo, haga clic en **Aceptar**.  
  
6.  Seleccione y elimine el **ReceiveRequest** y **SendResponse** actividades.  
  
7.  En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y un **Checkout_Receive** actividad en el **servicio secuencial** actividad.
