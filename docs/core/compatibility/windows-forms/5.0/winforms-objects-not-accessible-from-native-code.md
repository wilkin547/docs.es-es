---
title: 'Cambio importante: objetos de WinForms no accesibles desde código nativo'
description: Obtenga información sobre el cambio importante en .NET 5, donde los objetos de Windows Forms ya no son accesibles desde código nativo.
ms.date: 01/29/2021
ms.openlocfilehash: 823d37cb8115b8669b254878325a350809393e79
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256101"
---
# <a name="native-code-cant-access-windows-forms-objects"></a><span data-ttu-id="f59cd-103">El código nativo no puede acceder a objetos Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f59cd-103">Native code can't access Windows Forms objects</span></span>

<span data-ttu-id="f59cd-104">A partir de .NET 5, ya no puede tener acceso a objetos de Windows Forms desde código nativo.</span><span class="sxs-lookup"><span data-stu-id="f59cd-104">Starting in .NET 5, you can no longer access Windows Forms objects from native code.</span></span>

## <a name="change-description"></a><span data-ttu-id="f59cd-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f59cd-105">Change description</span></span>

<span data-ttu-id="f59cd-106">En versiones anteriores de .NET, algunos tipos de Windows Forms se representaban como visibles para la interoperabilidad COM y, por tanto, se podía tener acceso al código nativo.</span><span class="sxs-lookup"><span data-stu-id="f59cd-106">In previous .NET versions, some Windows Forms types were decorated as visible to COM interop, and thus were accessible to native code.</span></span> <span data-ttu-id="f59cd-107">A partir de .NET 5, no hay ninguna API de Windows Forms visible para la interoperabilidad COM o accesible para el código nativo.</span><span class="sxs-lookup"><span data-stu-id="f59cd-107">Starting in .NET 5, no Windows Forms API are visible to COM interop or accessible to native code.</span></span> <span data-ttu-id="f59cd-108">El entorno de ejecución de .NET ya no admite la creación de bibliotecas de tipos personalizados directamente.</span><span class="sxs-lookup"><span data-stu-id="f59cd-108">The .NET runtime no longer supports creating custom type libraries out of the box.</span></span> <span data-ttu-id="f59cd-109">Además, el entorno de ejecución de .NET no puede depender de la biblioteca de tipos para .NET Framework (lo que requeriría mantener la forma de las clases tal como estaban en .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="f59cd-109">In addition, the .NET runtime can't depend on the type library for .NET Framework (which would require maintaining the shape of classes as they were in .NET Framework).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f59cd-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f59cd-110">Reason for change</span></span>

- <span data-ttu-id="f59cd-111">Eliminación de `ComVisible(true)` de las enumeraciones que se usaron para la generación y búsqueda de la biblioteca de tipos (archivo TLB): como no hay ningún TLB de WinForms proporcionado por .NET Core, no hay ningún valor para mantener este atributo.</span><span class="sxs-lookup"><span data-stu-id="f59cd-111">Removal of `ComVisible(true)` from enumerations that were used for type library (TLB file) generation and lookup: Since there is no WinForms TLB provided by .NET Core, there's no value in keeping this attribute.</span></span>
- <span data-ttu-id="f59cd-112">Eliminación de `ComVisible(true)` de las clases `AccessibleObject`: las clases no son "CoCreateable" (no tienen ningún constructor sin parámetros), y la exposición de una instancia ya existente a COM no requiere ese atributo.</span><span class="sxs-lookup"><span data-stu-id="f59cd-112">Removal of `ComVisible(true)` from `AccessibleObject` classes: The classes are not CoCreateable (they have no parameterless constructor), and exposing an already existing instance to COM does not require that attribute.</span></span>
- <span data-ttu-id="f59cd-113">Eliminación de `ComVisible(true)` de las clases `Control` y `Component`: esto se usaba para permitir el hospedaje de controles de WinForms a través de OLE/ActiveX, por ejemplo en VB6 o MFC.</span><span class="sxs-lookup"><span data-stu-id="f59cd-113">Removal of `ComVisible(true)` from `Control` and `Component` classes: This was used to allow hosting of WinForms controls via OLE/ActiveX, for example in VB6 or MFC.</span></span> <span data-ttu-id="f59cd-114">Sin embargo, requiere un TLB para WinForms, que ya no se proporciona, así como la activación basada en el registro, que tampoco funcionaría de forma integrada.</span><span class="sxs-lookup"><span data-stu-id="f59cd-114">However, this requires a TLB for WinForms, which is no longer provided, as well as registry-based activation, which also would not work out of the box.</span></span> <span data-ttu-id="f59cd-115">Por lo general, no se ha realizado el mantenimiento del hospedaje basado en COM de los controles de WinForms, por lo que se ha quitado la compatibilidad en lugar de dejarla en un estado no admitido.</span><span class="sxs-lookup"><span data-stu-id="f59cd-115">Generally, there was no maintenance of COM-based hosting of WinForms controls, so support was removed instead of leaving it in an unsupported state.</span></span>
- <span data-ttu-id="f59cd-116">Eliminación de atributos `ClassInterface` de los controles: si no se admite el hospedaje a través de OLE/ActiveX, estos atributos ya no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="f59cd-116">Removal of `ClassInterface` attributes from controls: If hosting via OLE/ActiveX is not supported, these attributes aren't needed anymore.</span></span> <span data-ttu-id="f59cd-117">Se mantienen en otros lugares en los que los objetos todavía están expuestos a COM y el atributo puede ser pertinente.</span><span class="sxs-lookup"><span data-stu-id="f59cd-117">They are kept in other places where objects are still exposed to COM and the attribute may be relevant.</span></span>
- <span data-ttu-id="f59cd-118">Eliminación de `ComVisible(true)` de `EventArgs`: se usaban con más probabilidad con el hospedaje de OLE/ActiveX, que ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="f59cd-118">Removal of `ComVisible(true)` from `EventArgs`: They were most likely used with OLE/ActiveX hosting, which is no longer supported.</span></span> <span data-ttu-id="f59cd-119">Tampoco son "CoCreateable", por lo que el atributo no tiene ningún propósito.</span><span class="sxs-lookup"><span data-stu-id="f59cd-119">They are not CoCreateable either, so the attribute has no purpose.</span></span> <span data-ttu-id="f59cd-120">Además, la exposición de las instancias existentes sin proporcionar un TLB no tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="f59cd-120">Also, exposing existing instances without providing a TLB makes no sense.</span></span>
- <span data-ttu-id="f59cd-121">Eliminación de `ComVisible(true)` de delegados: se desconoce la finalidad, pero dado que ya no se admite el hospedaje de ActiveX de controles de WinForms, no es probable que tenga alguna utilidad.</span><span class="sxs-lookup"><span data-stu-id="f59cd-121">Removal of `ComVisible(true)` from delegates: Purpose is unknown, but since ActiveX hosting of WinForms Controls is no longer supported, it's unlikely to have any usefulness.</span></span>
- <span data-ttu-id="f59cd-122">Eliminación de `ComVisible(true)` de algún código no público: el único posible consumidor sería el nuevo diseñador de Visual Studio, pero sin un GUID especificado, no es probable que siga siendo necesario.</span><span class="sxs-lookup"><span data-stu-id="f59cd-122">Removal of `ComVisible(true)` from some non-public code: The only potential consumer would be the new Visual Studio designer, but without a GUID specified, it's unlikely that it's still needed.</span></span>
- <span data-ttu-id="f59cd-123">Eliminación de `ComVisible(true)` de algunas clases de diseñador público arbitrarias: es posible que el diseñador de Visual Studio anterior haya estado usando la interoperabilidad COM para comunicarse con estas clases.</span><span class="sxs-lookup"><span data-stu-id="f59cd-123">Removal of `ComVisible(true)` from some arbitrary public designer classes: The old Visual Studio designer may have been using COM interop to talk to these classes.</span></span> <span data-ttu-id="f59cd-124">Sin embargo, el antiguo diseñador no es compatible con .NET Core, por lo que pocas personas lo necesitarían como `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="f59cd-124">However, the old designer doesn't support .NET Core, so few people would need these as `ComVisible`.</span></span>
- <span data-ttu-id="f59cd-125">`IWin32Window` definió el mismo GUID que se definió en .NET Framework, que tiene consecuencias peligrosas.</span><span class="sxs-lookup"><span data-stu-id="f59cd-125">`IWin32Window` defined the same GUID that was defined in .NET Framework, which has dangerous consequences.</span></span> <span data-ttu-id="f59cd-126">Si requiere interoperabilidad con .NET Framework, utilice `ComImport`.</span><span class="sxs-lookup"><span data-stu-id="f59cd-126">If you require interop with .NET Framework, use `ComImport`.</span></span>
- <span data-ttu-id="f59cd-127">El `IDataObject` administrado por WinForms se hizo `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="f59cd-127">The WinForms managed `IDataObject` was made `ComVisible`.</span></span> <span data-ttu-id="f59cd-128">Esto no es necesario, hay una declaración de interfaz de `ComImport` independiente para la interoperabilidad COM de `IDataObject`.</span><span class="sxs-lookup"><span data-stu-id="f59cd-128">This is not required, there is a separate `ComImport` interface declaration for `IDataObject` COM interop.</span></span> <span data-ttu-id="f59cd-129">Es contraproducente que el `IDataObject` administrado sea `ComVisible`, ya que no se proporciona ningún TLB y la serialización siempre dará error.</span><span class="sxs-lookup"><span data-stu-id="f59cd-129">It's counterproductive to have the managed `IDataObject` be `ComVisible`, since no TLB is provided and marshaling will always fail.</span></span> <span data-ttu-id="f59cd-130">Además, no se especificó el GUID y se diferencia de .NET Framework, por lo que es poco probable que la eliminación de un IID no documentado afecte negativamente a los clientes.</span><span class="sxs-lookup"><span data-stu-id="f59cd-130">Also, the GUID was not specified and differed from .NET Framework, so its unlikely that removing an undocumented IID will affect customers negatively.</span></span>
- <span data-ttu-id="f59cd-131">Eliminación de `ComVisible(false)`: se colocan en lugares aparentemente arbitrarios y son redundantes cuando el valor predeterminado es no exponer clases a la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="f59cd-131">Removal of `ComVisible(false)`: Those are placed in seemingly arbitrary places and are redundant when the default is to not expose classes to COM interop.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f59cd-132">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f59cd-132">Version introduced</span></span>

<span data-ttu-id="f59cd-133">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f59cd-133">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f59cd-134">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f59cd-134">Recommended action</span></span>

<span data-ttu-id="f59cd-135">El ejemplo siguiente funciona en .NET Framework y .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f59cd-135">The following example works on .NET Framework and .NET Core 3.1.</span></span> <span data-ttu-id="f59cd-136">Este ejemplo se basa en la biblioteca de tipos de .NET Framework, que permite que el código JavaScript vuelva a llamar a la subclase del formulario mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="f59cd-136">This example relies on the .NET Framework type library, which allows the JavaScript to call back into the form subclass via reflection.</span></span>

```cs
[PermissionSet(SecurityAction.Demand, Name="FullTrust")]
[System.Runtime.InteropServices.ComVisibleAttribute(true)]
public class Form1 : Form
{
    private WebBrowser webBrowser1 = new WebBrowser();

    protected override void OnLoad(EventArgs e)
    {
        webBrowser1.AllowWebBrowserDrop = false;
        webBrowser1.IsWebBrowserContextMenuEnabled = false;
        webBrowser1.WebBrowserShortcutsEnabled = false;
        webBrowser1.ObjectForScripting = this;

        webBrowser1.DocumentText =
            "<html><body><button " +
            "onclick=\"window.external.Test('called from script code')\">" +
            "call client code from script code</button>" +
            "</body></html>";
    }

    public void Test(String message)
    {
        MessageBox.Show(message, "client code");
    }
}
```

<span data-ttu-id="f59cd-137">Hay dos formas posibles de hacer que el ejemplo funcione en .NET 5 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="f59cd-137">There are two possible ways to make the example work on .NET 5 and later versions:</span></span>

- <span data-ttu-id="f59cd-138">Introducir un objeto `ObjectForScripting` declarado por el usuario que admita `IDispatch` (que se aplica de forma predeterminada, a menos que se cambie explícitamente en el nivel de proyecto).</span><span class="sxs-lookup"><span data-stu-id="f59cd-138">Introduce a user-declared `ObjectForScripting` object that supports `IDispatch` (which is applied by default, unless changed explicitly at the project level).</span></span>

  ```cs
  public class MyScriptObject
  {
      private Form1 _form;

      public MyScriptObject(Form1 form)
      {
          _form = form;
      }

      public void Test(string message)
      {
          MessageBox.Show(message, "client code");
      }
  }

  public partial class Form1 : Form
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = new MyScriptObject(this);

          ...
      }
  }
  ```

- <span data-ttu-id="f59cd-139">Declarar una interfaz con los métodos que se van a exponer.</span><span class="sxs-lookup"><span data-stu-id="f59cd-139">Declare an interface with the methods to expose.</span></span>

  ```cs
  public interface IForm1
  {
      void Test(string message);
  }

  [ComDefaultInterface(typeof(IForm1))]
  public partial class Form1 : Form, IForm1
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = this;

          ...
      }
  }
  ```

## <a name="affected-apis"></a><span data-ttu-id="f59cd-140">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f59cd-140">Affected APIs</span></span>

<span data-ttu-id="f59cd-141">Todas las API de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f59cd-141">All Windows Forms APIs.</span></span>

<!--

### Category

- Windows Forms

-->
