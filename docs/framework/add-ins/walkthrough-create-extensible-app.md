---
title: 'Tutorial: Crear una aplicación extensible'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080727"
---
# <a name="walkthrough-creating-an-extensible-application"></a>Tutorial: Crear una aplicación extensible
Este tutorial describe cómo crear una canalización para un complemento que realiza funciones de la calculadora simple. No se muestra un escenario real; en su lugar, muestra la funcionalidad básica de una canalización y cómo un complemento puede proporcionar servicios para un host.  
  
 En este tutorial se describe las tareas siguientes:  
  
-   Creación de una solución de Visual Studio.  
  
-   Creación de la estructura de directorios de la canalización.  
  
-   Crear el contrato y vistas.  
  
-   Crear el adaptador de conversión.  
  
-   Crear el adaptador del host.  
  
-   Crear el host.  
  
-   Crear el complemento.  
  
-   Implementar la canalización.  
  
-   Ejecutar la aplicación host.  
  
 Esta canalización sólo pasa tipos serializables (<xref:System.Double> y <xref:System.String>), entre el host y el complemento. Para obtener un ejemplo que muestra cómo pasar colecciones de tipos de datos complejos, vea [Tutorial: pasar colecciones entre Hosts y complementos](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).  
  
 El contrato de esta canalización define un modelo de objetos de cuatro operaciones aritméticas: agregar, restar, multiplicar y dividir. El host proporciona el complemento con una ecuación para calcular, por ejemplo, 2 + 2, y el complemento devuelve el resultado al host.  
  
 Versión 2 del complemento de calculadora proporciona otras posibilidades de cálculo y muestra el control de versiones. Se describe en [Tutorial: habilitar la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesitas lo siguiente para poder llevar a cabo este tutorial:  
  
-   Visual Studio.  
  
## <a name="creating-a-visual-studio-solution"></a>Creación de una solución de Visual Studio  
 Utilice una solución de Visual Studio que contenga los proyectos de los segmentos de canalización.  
  
#### <a name="to-create-the-pipeline-solution"></a>Para crear la solución de canalización  
  
1.  En Visual Studio, cree un nuevo proyecto denominado `Calc1Contract`. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  Nombre de la solución `CalculatorV1`.  
  
## <a name="creating-the-pipeline-directory-structure"></a>Creación de la estructura de directorios de canalización  
 El modelo del complemento requiere que los ensamblados de segmento de canalización se coloquen en una estructura de directorios especificado. Para obtener más información acerca de la estructura de la canalización, consulte [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>Para crear la estructura de directorios de canalización  
  
1.  Cree una carpeta de la aplicación en cualquier lugar en el equipo.  
  
2.  En esa carpeta, cree la siguiente estructura:  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     No es necesario poner la estructura de carpetas de la canalización en la carpeta de aplicación; se hace aquí solo por comodidad. En el paso correspondiente, el tutorial explica cómo cambiar el código si la estructura de carpetas de la canalización está en una ubicación diferente. Vea la explicación de los requisitos de directorio de canalización en [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
    > [!NOTE]
    >  El `CalcV2` carpeta no se usa en este tutorial; es un marcador de posición para [Tutorial: habilitar la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).  
  
## <a name="creating-the-contract-and-views"></a>Crear el contrato y vistas  
 El segmento de contrato de esta canalización define la `ICalc1Contract` interfaz, que define cuatro métodos: `add`, `subtract`, `multiply`, y `divide`.  
  
#### <a name="to-create-the-contract"></a>Para crear el contrato  
  
1.  En la solución de Visual Studio denominada `CalculatorV1`, abra el `Calc1Contract` proyecto.  
  
2.  En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1Contract` proyecto:  
  
     System.AddIn.Contract.dll  
  
     System.AddIn.dll  
  
3.  En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos.  
  
4.  En **el Explorador de soluciones**, agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla. En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalc1Contract`.  
  
5.  En el archivo de interfaz, agregue referencias de espacio de nombres a <xref:System.AddIn.Contract> y <xref:System.AddIn.Pipeline>.  
  
6.  Utilice el código siguiente para completar este segmento de contrato. Tenga en cuenta que esta interfaz debe tener el <xref:System.AddIn.Pipeline.AddInContractAttribute> atributo.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  Si lo desea, compile la solución de Visual Studio. La solución no se puede ejecutar hasta que corrija el procedimiento final, pero compila después de cada procedimiento garantiza que cada proyecto.  
  
 Como la vista de complemento y el host de la vista de complemento suelen tener el mismo código, especialmente en la primera versión de un complemento, puede crear fácilmente las vistas al mismo tiempo. Se diferencian en un solo factor: la vista de complemento requiere el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo, mientras que la vista host del complemento no requiere ningún atributo.  
  
#### <a name="to-create-the-add-in-view"></a>Para crear la vista de complemento  
  
1.  Agregue un nuevo proyecto denominado `Calc1AddInView` a la `CalculatorV1` solución. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  En **el Explorador de soluciones**, agregue una referencia a System.AddIn.dll a la `Calc1AddInView` proyecto.  
  
3.  En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla. En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.  
  
4.  En el archivo de interfaz, agregue una referencia de espacio de nombres a <xref:System.AddIn.Pipeline>.  
  
5.  Utilice el código siguiente para completar esta vista de complemento. Tenga en cuenta que esta interfaz debe tener el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  Si lo desea, compile la solución de Visual Studio.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>Para crear la vista de host del complemento:  
  
1.  Agregue un nuevo proyecto denominado `Calc1HVA` a la `CalculatorV1` solución. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla. En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.  
  
3.  En el archivo de interfaz, utilice el código siguiente para completar la vista host del complemento.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  Si lo desea, compile la solución de Visual Studio.  
  
## <a name="creating-the-add-in-side-adapter"></a>Crear el adaptador de conversión  
 Este adaptador de conversión consta de un adaptador de vista a contrato. Este segmento de canalización convierte a los tipos de la vista de complemento, el contrato.  
  
 En esta canalización, el complemento proporciona un servicio al host y los tipos que fluyen desde el complemento al host. Dado que no hay tipos fluyen desde el host para el complemento, no es necesario incluir un adaptador de contrato a vista en el lado del complemento de esta canalización.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>Para crear el adaptador de conversión  
  
1.  Agregue un nuevo proyecto denominado `Calc1AddInSideAdapter` a la `CalculatorV1` solución. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1AddInSideAdapter` proyecto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Agregue referencias a los proyectos para los segmentos de canalización adyacente:  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**. En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias de proyecto.  
  
5.  Cambiar el nombre de la clase del proyecto predeterminado `CalculatorViewToContractAddInSideAdapter`.  
  
6.  En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.  
  
7.  En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcAddInViews` y `CalculatorContracts`. (En Visual Basic, estas referencias de espacio de nombres son `Calc1AddInView.CalcAddInViews` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)  
  
8.  Aplicar el <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo a la `CalculatorViewToContractAddInSideAdapter` (clase), que la identifica como el adaptador de conversión.  
  
9. Realizar el `CalculatorViewToContractAddInSideAdapter` heredan de la clase <xref:System.AddIn.Pipeline.ContractBase>, que proporciona una implementación predeterminada de la <xref:System.AddIn.Contract.IContract> interfaz e implemente la interfaz del contrato de la canalización, `ICalc1Contract`.  
  
10. Agregue un constructor público que acepta un `ICalculator`, lo almacena en caché en un campo privado y llama al constructor de clase base.  
  
11. Para implementar los miembros de `ICalc1Contract`, basta con llamar a los miembros correspondientes de la `ICalculator` instancia que se pasa al constructor y devolver los resultados. Esto adapta a la vista (`ICalculator`) para el contrato (`ICalc1Contract`).  
  
     El código siguiente muestra el adaptador de conversión completado.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. Si lo desea, compile la solución de Visual Studio.  
  
## <a name="creating-the-host-side-adapter"></a>Crear el adaptador del Host  
 Este adaptador del host se compone de un adaptador de contrato a vista. Este segmento adapta el contrato a la vista de host del complemento.  
  
 En esta canalización, el complemento proporciona un servicio que el host y el flujo de tipos desde el complemento al host. Dado que no hay tipos fluyen desde el host para el complemento, no es necesario incluir un adaptador de vista a contrato.  
  
 Para implementar la administración de la duración, use un <xref:System.AddIn.Pipeline.ContractHandle> objeto va a asociar un token de duración del contrato. Debe mantener una referencia a este identificador en orden para que funcione la administración de vigencia. Después de que se aplica el token, ninguna programación adicional es necesaria porque el sistema del complemento puede desechar objetos cuando ya no se usan y que estén disponibles para la recolección. Para obtener más información, consulte [administración de la duración](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).  
  
#### <a name="to-create-the-host-side-adapter"></a>Para crear el adaptador del host  
  
1.  Agregue un nuevo proyecto denominado `Calc1HostSideAdapter` a la `CalculatorV1` solución. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1HostSideAdapter` proyecto:  
  
     System.AddIn.dll  
  
     System.AddIn.Contract.dll  
  
3.  Agregue referencias a los proyectos en los segmentos adyacentes:  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**. En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias de proyecto.  
  
5.  Cambiar el nombre de la clase del proyecto predeterminado `CalculatorContractToViewHostSideAdapter`.  
  
6.  En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.  
  
7.  En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcHVAs` y `CalculatorContracts`. (En Visual Basic, estas referencias de espacio de nombres son `Calc1HVA.CalcHVAs` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)  
  
8.  Aplicar el <xref:System.AddIn.Pipeline.HostAdapterAttribute> atributo a la `CalculatorContractToViewHostSideAdapter` (clase), que la identifica como el segmento del adaptador del host.  
  
9. Realizar el `CalculatorContractToViewHostSideAdapter` clase implementa la interfaz que representa la vista host del complemento: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` en Visual Basic).  
  
10. Agregue un constructor público que acepta el tipo de contrato de la canalización, `ICalc1Contract`. El constructor debe almacenar en caché la referencia al contrato. También debe crear y almacenar en caché un nuevo <xref:System.AddIn.Pipeline.ContractHandle> para el contrato, para administrar la vigencia del complemento.  
  
    > [!IMPORTANT]
    >  El <xref:System.AddIn.Pipeline.ContractHandle> es fundamental para la administración de la duración. Si no puede mantener una referencia a la <xref:System.AddIn.Pipeline.ContractHandle> objeto recolección lo reclamará y la canalización se cerrará cuando el programa no lo espera. Esto puede conducir a errores que son difíciles de diagnosticar, como <xref:System.AppDomainUnloadedException>. Cierre es una fase normal en la vida de una canalización, por lo que no hay ninguna manera de que el código de administración de vigencia detectar que esta condición es un error.  
  
11. Para implementar los miembros de `ICalculator`, basta con llamar a los miembros correspondientes de la `ICalc1Contract` instancia que se pasa al constructor y devolver los resultados. Esto adapta el contrato (`ICalc1Contract`) a la vista (`ICalculator`).  
  
     El código siguiente muestra el adaptador del host completado.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. Si lo desea, compile la solución de Visual Studio.  
  
## <a name="creating-the-host"></a>Crear el Host  
 Una aplicación host interactúa con el complemento a través de la vista host del complemento. Usa el complemento detección y activación métodos proporcionados por el <xref:System.AddIn.Hosting.AddInStore> y <xref:System.AddIn.Hosting.AddInToken> clases para hacer lo siguiente:  
  
-   Actualizar la caché de información de canalización y complemento.  
  
-   Buscar complementos del tipo de vista de host, `ICalculator`, bajo el directorio raíz de la canalización especificada.  
  
-   Solicitar al usuario que especifique que complemento para usar.  
  
-   Activar el complemento seleccionado en un nuevo dominio de aplicación con un nivel de confianza de seguridad especificado.  
  
-   Ejecute personalizado `RunCalculator` método, que llama a métodos del complemento según lo especificado por la vista host del complemento.  
  
#### <a name="to-create-the-host"></a>Para crear el host  
  
1.  Agregue un nuevo proyecto denominado `Calc1Host` a la `CalculatorV1` solución. Basarlo en el **aplicación de consola** plantilla.  
  
2.  En **el Explorador de soluciones**, agregue una referencia al ensamblado System.AddIn.dll para el `Calc1Host` proyecto.  
  
3.  Agregar una referencia al proyecto el `Calc1HVA` proyecto. Seleccione la referencia del proyecto y en **propiedades** establecer **Copy Local** a **False**. En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False**.  
  
4.  Cambiar el nombre del archivo de clase (módulo en Visual Basic) `MathHost1`.  
  
5.  En Visual Basic, utilice el **aplicación** pestaña de la **las propiedades del proyecto** cuadro de diálogo para establecer **objeto Startup** a **Sub Main**.  
  
6.  En el archivo de clase o módulo, agregue una referencia de espacio de nombres a <xref:System.AddIn.Hosting>.  
  
7.  En el archivo de clase o módulo, agregue una referencia de espacio de nombres para la vista de host del complemento: `CalcHVAs`. (En Visual Basic, esta referencia de espacio de nombres es `Calc1HVA.CalcHVAs`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)  
  
8.  En **el Explorador de soluciones**, seleccione la solución y desde el **proyecto** menú elija **propiedades**. En el **páginas de propiedades de la solución** cuadro de diálogo, establezca el **proyecto de inicio único** sea este proyecto de aplicación host.  
  
9. En el archivo de clase o módulo, use el <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> método para actualizar la memoria caché. Utilice la <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> método para obtener una colección de tokens y utilice el <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> método para activar un complemento.  
  
     El código siguiente muestra la aplicación host completada.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  Este código supone que la estructura de carpetas de la canalización se encuentra en la carpeta de la aplicación. Si se encuentra en otro lugar, cambie la línea de código que establece el `addInRoot` variable, por lo que la variable contiene la ruta de acceso a la estructura de directorios de canalización.  
  
     El código usa un `ChooseCalculator` método para enumerar los tokens y para pedir al usuario elegir un complemento. El `RunCalculator` método pide al usuario para expresiones matemáticas simples, analiza las expresiones utilizando la `Parser` clase y muestra los resultados devuelven por el complemento.  
  
10. Si lo desea, compile la solución de Visual Studio.  
  
## <a name="creating-the-add-in"></a>Crear el complemento  
 Un complemento implementa los métodos especificados por la vista de complemento. Este complemento implementa el `Add`, `Subtract`, `Multiply`, y `Divide` operaciones y devuelve los resultados al host.  
  
#### <a name="to-create-the-add-in"></a>Para crear el complemento  
  
1.  Agregue un nuevo proyecto denominado `AddInCalcV1` a la `CalculatorV1` solución. Basarlo en el **biblioteca de clases** plantilla.  
  
2.  En **el Explorador de soluciones**, agregue una referencia al ensamblado System.AddIn.dll al proyecto.  
  
3.  Agregar una referencia al proyecto el `Calc1AddInView` proyecto. Seleccione la referencia del proyecto y en **propiedades**, establezca **Copy Local** a **False**. En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para la referencia del proyecto.  
  
4.  Cambiar el nombre de la clase `AddInCalcV1`.  
  
5.  En el archivo de clase, agregue una referencia de espacio de nombres a <xref:System.AddIn> y el segmento de vista de complemento: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` en Visual Basic).  
  
6.  Aplicar el <xref:System.AddIn.AddInAttribute> atributo a la `AddInCalcV1` (clase), para identificar la clase como un complemento.  
  
7.  Realizar el `AddInCalcV1` clase implementa la interfaz que representa la vista de complemento: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` en Visual Basic).  
  
8.  Implemente los miembros de `ICalculator` devolviendo los resultados de los cálculos correspondientes.  
  
     El código siguiente muestra el complemento completado.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. Si lo desea, compile la solución de Visual Studio.  
  
## <a name="deploying-the-pipeline"></a>Implementación de la canalización  
 Ahora está listo para compilar e implementar los segmentos de complemento a la estructura de directorios de canalización requerida.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>Para implementar los segmentos en la canalización  
  
1.  En cada proyecto de la solución, utilice el **compilar** ficha de **las propiedades del proyecto** (el **compilar** pestaña en Visual Basic) para establecer el valor de la **ruta de acceso de salida**  (el **ruta de acceso de salida de compilación** en Visual Basic). Si el nombre de la carpeta aplicación `MyApp`, por ejemplo, podrían compilar sus proyectos en las siguientes carpetas:  
  
    |Proyecto|Ruta de acceso|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|MyApp|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|MyApp|  
  
    > [!NOTE]
    >  Si ha decidido poner la estructura de carpetas de la canalización en una ubicación distinta a la carpeta de aplicación, debe modificar las rutas de acceso que se muestra en la tabla en consecuencia. Vea la explicación de los requisitos de directorio de canalización en [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
2.  Compile la solución de Visual Studio.  
  
3.  Compruebe los directorios de la canalización y la aplicación para asegurarse de que los ensamblados se copiaron en los directorios correctos y que ninguna copia adicional de los ensamblados se instala en las carpetas incorrectas.  
  
    > [!NOTE]
    >  Si no cambió **Copy Local** a **False** para el `Calc1AddInView` referencia de proyecto la `AddInCalcV1` proyectos, problemas de cargador contexto impedirá que el complemento que se encuentra.  
  
     Para obtener información acerca de la implementación a la canalización, consulte [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
## <a name="running-the-host-application"></a>Ejecutar la aplicación Host  
 Ahora está listo para ejecutar el host e interactuar con el complemento.  
  
#### <a name="to-run-the-host-application"></a>Para ejecutar la aplicación host  
  
1.  En el símbolo del sistema, vaya al directorio de la aplicación y ejecutar la aplicación host, `Calc1Host.exe`.  
  
2.  El host busca todos los complementos disponibles de su tipo y se le pide que seleccione un complemento. Escriba **1** para el complemento solo está disponible.  
  
3.  Escriba una ecuación para la Calculadora, como **2 + 2**. Debe haber espacios entre los números y el operador.  
  
4.  Tipo **salir** y presione la **ENTRAR** tecla para cerrar la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Habilitar la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [Tutorial: Pasar colecciones entre Hosts y complementos](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [Requisitos del desarrollo de canalizaciones](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [Contratos, vistas y adaptadores](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Desarrollo de canalizaciones](../../../docs/framework/add-ins/pipeline-development.md)
