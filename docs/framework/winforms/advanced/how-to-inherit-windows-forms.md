---
title: Procedimiento para heredar formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 0d8799359a12b9bb64331d83df2500bede8c0ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314549"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="74437-102">Procedimiento para heredar formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="74437-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="74437-103">Crear nuevos Windows Forms heredando de formularios base es una forma práctica de aprovechar el trabajo ya hecho sin tener que pasar por todo el proceso de crear un formulario cada vez que lo necesite.</span><span class="sxs-lookup"><span data-stu-id="74437-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="74437-104">Para obtener más información acerca de la herencia de formularios en tiempo de diseño mediante el **selector de herencia** cuadro de diálogo y cómo distinguir visualmente los niveles de seguridad de los controles heredados, vea [Cómo: Heredar formularios mediante el cuadro de diálogo Selector de herencia](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="74437-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="74437-105">**Nota**: Para heredar de un formulario, el archivo o el espacio de nombres que contiene el formulario debe haberse compilado en un archivo ejecutable o DLL.</span><span class="sxs-lookup"><span data-stu-id="74437-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="74437-106">Para compilar el proyecto, elija **Compilar** en el menú **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="74437-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="74437-107">Además, debe agregarse una referencia al espacio de nombres a la clase que hereda el formulario.</span><span class="sxs-lookup"><span data-stu-id="74437-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="74437-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="74437-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="74437-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="74437-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="74437-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="74437-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="74437-111">Para heredar un formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="74437-111">To inherit a form programmatically</span></span>  
  
1. <span data-ttu-id="74437-112">En la clase, agregue una referencia al espacio de nombres que contiene el formulario del que desea heredar.</span><span class="sxs-lookup"><span data-stu-id="74437-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2. <span data-ttu-id="74437-113">En la definición de la clase, agregue una referencia al formulario del que se va a heredar.</span><span class="sxs-lookup"><span data-stu-id="74437-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="74437-114">La referencia debe incluir el espacio de nombres que contiene el formulario, seguido por un punto y del nombre del propio formulario base.</span><span class="sxs-lookup"><span data-stu-id="74437-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="74437-115">Al heredar formularios, tenga en cuenta que pueden surgir problemas por controladores de eventos a los que se llama dos veces, porque cada evento está siendo controlado por la clase base y por la clase heredada.</span><span class="sxs-lookup"><span data-stu-id="74437-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="74437-116">Para más información acerca de cómo evitar este problema, vea [Solución de problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="74437-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74437-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="74437-117">See also</span></span>

- [<span data-ttu-id="74437-118">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="74437-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="74437-119">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="74437-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="74437-120">using</span><span class="sxs-lookup"><span data-stu-id="74437-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="74437-121">Efectos de modificar la apariencia de un formulario base</span><span class="sxs-lookup"><span data-stu-id="74437-121">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="74437-122">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="74437-122">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
