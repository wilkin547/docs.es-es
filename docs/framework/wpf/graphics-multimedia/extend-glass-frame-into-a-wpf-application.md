---
title: Ampliar el marco de vidrio en una aplicación de WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: a702456895cfdbd44a58059befefb69deee5afa3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636203"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="7c304-102">Ampliar el marco de vidrio en una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="7c304-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="7c304-103">En este tema se muestra cómo extender el marco Glass de Windows Vista en el área cliente de una aplicación Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="7c304-103">This topic demonstrates how to extend the Windows Vista glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="7c304-104">Este ejemplo solo funcionará en un equipo con Windows Vista que ejecute el Administrador de ventanas de escritorio (DWM) con Glass habilitado.</span><span class="sxs-lookup"><span data-stu-id="7c304-104">This example will only work on a Windows Vista machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="7c304-105">Windows Vista Home Basic Edition no admite el efecto de cristal transparente.</span><span class="sxs-lookup"><span data-stu-id="7c304-105">Windows Vista Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="7c304-106">Las áreas que normalmente se representarían con el efecto de cristal transparente en otras ediciones de Windows Vista se representan opacas.</span><span class="sxs-lookup"><span data-stu-id="7c304-106">Areas that would typically render with the transparent glass effect on other editions of Windows Vista are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="7c304-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c304-107">Example</span></span>

<span data-ttu-id="7c304-108">En la imagen siguiente se muestra el marco Glass extendido en la barra de direcciones de Internet Explorer 7:</span><span class="sxs-lookup"><span data-stu-id="7c304-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![Captura de pantalla que muestra el marco de cristal ampliado detrás de la barra de direcciones de IE7.](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="7c304-110">Para extender el marco Glass en una aplicación WPF, se necesita acceso a la API no administrada.</span><span class="sxs-lookup"><span data-stu-id="7c304-110">To extend the glass frame on a WPF application, access to unmanaged API is needed.</span></span> <span data-ttu-id="7c304-111">En el ejemplo de código siguiente se realiza una invocación de plataforma (PInvoke) para las dos API necesarias para extender el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="7c304-111">The following code example does a Platform Invoke (pinvoke) for the two API needed to extend the frame into the client area.</span></span> <span data-ttu-id="7c304-112">Cada una de estas API se declaran en una clase denominada **NonClientRegionAPI**.</span><span class="sxs-lookup"><span data-stu-id="7c304-112">Each of these API are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="7c304-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) es la función de DWM que amplia el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="7c304-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="7c304-114">Toma dos parámetros; un identificador de ventana y una estructura [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins).</span><span class="sxs-lookup"><span data-stu-id="7c304-114">It takes two parameters; a window handle and a [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) structure.</span></span> <span data-ttu-id="7c304-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) se usa para indicarle al DWM cuánto más debe ampliarse el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="7c304-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="7c304-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c304-116">Example</span></span>

<span data-ttu-id="7c304-117">Para usar la función [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea), debe obtenerse un identificador de ventana.</span><span class="sxs-lookup"><span data-stu-id="7c304-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="7c304-118">En WPF, el identificador de ventana se puede obtener de la propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> de una <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="7c304-118">In WPF, the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="7c304-119">En el ejemplo siguiente, el marco se extiende en el área cliente del evento <xref:System.Windows.FrameworkElement.Loaded> de la ventana.</span><span class="sxs-lookup"><span data-stu-id="7c304-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="7c304-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c304-120">Example</span></span>

<span data-ttu-id="7c304-121">En el ejemplo siguiente se muestra una ventana simple en la que el marco se amplía en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="7c304-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="7c304-122">El marco se extiende detrás del borde superior que contiene los dos objetos <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="7c304-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="7c304-123">En la imagen siguiente se muestra el marco Glass extendido en una aplicación WPF:</span><span class="sxs-lookup"><span data-stu-id="7c304-123">The following image illustrates the glass frame extended into a WPF application:</span></span>

![Captura de pantalla que muestra un marco de cristal ampliado en una aplicación WPF.](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="7c304-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c304-125">See also</span></span>

- [<span data-ttu-id="7c304-126">Información general de Administrador de ventanas de escritorio</span><span class="sxs-lookup"><span data-stu-id="7c304-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="7c304-127">Información general sobre desenfoque Administrador de ventanas de escritorio</span><span class="sxs-lookup"><span data-stu-id="7c304-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- <span data-ttu-id="7c304-128">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) (DwmExtendFrameIntoClientArea [función])</span><span class="sxs-lookup"><span data-stu-id="7c304-128">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)</span></span>
