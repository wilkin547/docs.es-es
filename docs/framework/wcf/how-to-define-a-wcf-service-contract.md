---
title: 'Tutorial: definición de un contrato de servicio de Windows Communication Foundation'
description: Obtenga información sobre cómo definir un contrato de servicios como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246316"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: definición de un contrato de servicio de Windows Communication Foundation

En este tutorial se describe la primera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

Al crear un servicio WCF, la primera tarea es definir un contrato de servicio. El contrato de servicio especifica qué operaciones admite este. Una operación se puede considerar un método de servicio Web. Cree contratos de servicio mediante la definición de una interfaz de C# o Visual Basic. Una interfaz tiene las siguientes características:

- Cada método de la interfaz corresponde a una operación de servicio específica.
- Para cada interfaz, debe aplicar el <xref:System.ServiceModel.ServiceContractAttribute> atributo.
- Para cada operación o método, debe aplicar el <xref:System.ServiceModel.OperationContractAttribute> atributo.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Cree un proyecto de **biblioteca de servicios WCF** .
> - Defina una interfaz de contrato de servicio.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Crear un proyecto de biblioteca de servicios WCF y definir una interfaz de contrato de servicio

1. Abra Visual Studio como administrador. Para ello, seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **más**  >  **Ejecutar como administrador** en el menú contextual.

2. Cree un proyecto de **biblioteca de servicios WCF** .

   1. En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

   2. En el cuadro de diálogo **nuevo proyecto** , en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione la categoría **WCF** . Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana. Seleccione **biblioteca de servicios WCF**.

      > [!NOTE]
      > Si no ve la categoría de plantilla de proyecto de **WCF** , es posible que deba instalar el componente de **Windows Communication Foundation** de Visual Studio. En el cuadro de diálogo **nuevo proyecto** , seleccione el vínculo **abrir instalador de Visual Studio** en el lado izquierdo. Seleccione la pestaña **componentes individuales** y busque y seleccione **Windows Communication Foundation** en la categoría **actividades de desarrollo** . Elija **modificar** para iniciar la instalación del componente.

   3. En la sección inferior de la ventana, escriba *GettingStartedLib* para el **nombre** y *gettingstarted* para el **nombre**de la solución.

   4. Seleccione **Aceptar**.

      Visual Studio crea el proyecto, que tiene tres archivos: *IService1.CS* (o *IService1. VB* para un proyecto Visual Basic), *Service1.CS* (o *Service1. vb* para un proyecto Visual Basic) y *App.config*. Visual Studio define estos archivos como se indica a continuación:
      - El archivo *IService1* contiene la definición predeterminada del contrato de servicio.
      - El archivo *Service1* contiene la implementación predeterminada del contrato de servicio.
      - El archivo de *App.config* contiene la información de configuración necesaria para cargar el servicio predeterminado con la herramienta host de servicio WCF de Visual Studio. Para obtener más información acerca de la herramienta host de servicio WCF, vea [host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Si instaló Visual Studio con Visual Basic configuración del entorno del desarrollador, puede que la solución esté oculta. En este caso, seleccione **Opciones** en el menú **herramientas** y, a continuación, seleccione **proyectos y soluciones**  >  **General** en la ventana **Opciones** . Seleccione **Mostrar solución siempre**. Además, compruebe que la opción **Guardar nuevos proyectos al crear** está seleccionada.

3. En **Explorador de soluciones**, abra el archivo **IService1.CS** o **IService1. VB** y reemplace su código por el código siguiente:

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     Este contrato define una calculadora en línea. Observe que la `ICalculator` interfaz está marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo (simplificado como `ServiceContract` ). Este atributo define un espacio de nombres para eliminar la ambigüedad del nombre del contrato. El código marca cada operación de la calculadora con el <xref:System.ServiceModel.OperationContractAttribute> atributo (simplificado como `OperationContract` ).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Cree un proyecto de biblioteca de servicios WCF.
> - Defina una interfaz de contrato de servicio.

Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: implementar un contrato de servicio WCF](how-to-implement-a-wcf-contract.md)
