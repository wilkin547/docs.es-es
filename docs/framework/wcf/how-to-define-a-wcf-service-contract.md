---
title: 'Tutorial: Definir un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184092"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: Definir un contrato de servicio de Windows Communication Foundation

En este tutorial se describe la primera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .

Al crear un servicio WCF, la primera tarea consiste en definir un contrato de servicio. El contrato de servicio especifica qué operaciones admite este. Una operación se puede considerar un método de servicio Web. Los contratos de servicio se crean mediante la definición de una interfaz de Visual Basic o de C. Una interfaz tiene las siguientes características:

- Cada método de la interfaz corresponde a una operación de servicio específica.
- Para cada interfaz, <xref:System.ServiceModel.ServiceContractAttribute> debe aplicar el atributo.
- Para cada operación/método, <xref:System.ServiceModel.OperationContractAttribute> debe aplicar el atributo.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Crear un proyecto de biblioteca de servicios **WCF.**
> - Defina una interfaz de contrato de servicio.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Cree un proyecto de biblioteca de servicios WCF y defina una interfaz de contrato de servicio

1. Abra Visual Studio como administrador. Para ello, seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **Más** > **ejecución como administrador** en el menú contextual.

2. Crear un proyecto de biblioteca de servicios **WCF.**

   1. En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

   2. En el cuadro de diálogo **Nuevo proyecto,** en el lado izquierdo, expanda **Visual C** o **Visual Basic**y, a continuación, seleccione la categoría **WCF.** Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana. Seleccione **Biblioteca de servicios WCF**.

      > [!NOTE]
      > Si no ve la categoría de plantilla de proyecto **WCF,** es posible que deba instalar el componente **de Windows Communication Foundation** de Visual Studio. En el cuadro de diálogo **Nuevo proyecto,** seleccione el vínculo Abrir instalador de **Visual Studio** en el lado izquierdo. Seleccione la pestaña **Componentes individuales** y, a continuación, busque y seleccione **Windows Communication Foundation** en la categoría Actividades de **desarrollo.** Elija **Modify (Modificar)** para comenzar a instalar el componente.

   3. En la sección inferior de la ventana, escriba *GettingStartedLib* para **el nombre** y *GettingStarted* para el nombre de la **solución**.

   4. Seleccione **Aceptar**.

      Visual Studio crea el proyecto, que tiene tres archivos: *IService1.cs* (o *IService1.vb* para un proyecto de Visual Basic), *Service1.cs* (o *Service1.vb* para un proyecto de Visual Basic) y *App.config*. Visual Studio define estos archivos de la siguiente manera:
      - El archivo *IService1* contiene la definición predeterminada del contrato de servicio.
      - El archivo *Service1* contiene la implementación predeterminada del contrato de servicio.
      - El archivo *App.config* contiene la información de configuración necesaria para cargar el servicio predeterminado con la herramienta Host de servicio WCF de Visual Studio. Para obtener más información acerca de la herramienta Host de servicio WCF, vea Host de [servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Si instaló Visual Studio con la configuración del entorno de desarrollador de Visual Basic, la solución podría estar oculta. Si este es el caso, seleccione **Opciones** en el menú **Herramientas** y, a continuación, seleccione **Proyectos y soluciones** > **generales** en la ventana **Opciones.** Seleccione **Mostrar siempre la solución**. Además, compruebe que **Guardar nuevos proyectos cuando se cree** está seleccionado.

3. En el Explorador de **soluciones**, abra el archivo **IService1.cs** o **IService1.vb** y reemplace su código por el código siguiente:

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

     Este contrato define una calculadora en línea. Observe `ICalculator` que la interfaz está marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo (simplificado como `ServiceContract`). Este atributo define un espacio de nombres para desambiguar el nombre del contrato. El código marca cada <xref:System.ServiceModel.OperationContractAttribute> operación de `OperationContract`calculadora con el atributo (simplificado como ).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Crear un proyecto de biblioteca de servicios WCF.
> - Defina una interfaz de contrato de servicio.

Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: Implementar un contrato de servicio WCF](how-to-implement-a-wcf-contract.md)
