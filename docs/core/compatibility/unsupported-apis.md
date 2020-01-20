---
title: API no admitidas en .NET Core
description: Obtenga información sobre qué API de .NET Framework siempre producen una excepción en .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901347"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="32186-103">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="32186-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="32186-104">Las siguientes API siempre producen una excepción <xref:System.PlatformNotSupportedException> cuando se ejecutan en .NET Core en la plataforma especificada.</span><span class="sxs-lookup"><span data-stu-id="32186-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="32186-105">En este artículo se organizan los miembros de API afectados por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="32186-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="32186-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="32186-106">This article is a work-in-progress.</span></span> <span data-ttu-id="32186-107">No es una lista completa de las API que producen excepciones en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32186-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="32186-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que se inician en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32186-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="32186-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="32186-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="32186-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="32186-110">System</span></span>

| <span data-ttu-id="32186-111">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-111">Member</span></span> | <span data-ttu-id="32186-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-113">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="32186-114">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="32186-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="32186-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-117">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="32186-118">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="32186-119">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="32186-120">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-121">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="32186-122">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="32186-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="32186-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="32186-124">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-124">Member</span></span> | <span data-ttu-id="32186-125">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-126">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-127">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-128">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="32186-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="32186-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="32186-130">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-130">Member</span></span> | <span data-ttu-id="32186-131">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-132">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-133">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="32186-134">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="32186-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="32186-135">System.Configuration</span></span>

| <span data-ttu-id="32186-136">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-136">Member</span></span> | <span data-ttu-id="32186-137">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="32186-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="32186-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="32186-139">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="32186-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="32186-140">System.Console</span></span>

| <span data-ttu-id="32186-141">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-141">Member</span></span> | <span data-ttu-id="32186-142">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="32186-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-143">Linux and macOS</span></span> |
| <span data-ttu-id="32186-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-145">Linux and macOS</span></span> |
| <span data-ttu-id="32186-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-147">Linux and macOS</span></span> |
| <span data-ttu-id="32186-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-149">Linux and macOS</span></span> |
| <span data-ttu-id="32186-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="32186-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="32186-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-154">Linux and macOS</span></span> |
| <span data-ttu-id="32186-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="32186-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="32186-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-156">Linux and macOS</span></span> |
| <span data-ttu-id="32186-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-158">Linux and macOS</span></span> |
| <span data-ttu-id="32186-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-160">Linux and macOS</span></span> |
| <span data-ttu-id="32186-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-162">Linux and macOS</span></span> |
| <span data-ttu-id="32186-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="32186-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="32186-165">System.Data.Common</span></span>

| <span data-ttu-id="32186-166">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-166">Member</span></span> | <span data-ttu-id="32186-167">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="32186-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="32186-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="32186-169">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="32186-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="32186-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="32186-171">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-171">Member</span></span> | <span data-ttu-id="32186-172">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="32186-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-174">Linux</span><span class="sxs-lookup"><span data-stu-id="32186-174">Linux</span></span> |
| <span data-ttu-id="32186-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-176">Linux</span><span class="sxs-lookup"><span data-stu-id="32186-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="32186-177">macOS</span><span class="sxs-lookup"><span data-stu-id="32186-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="32186-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="32186-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="32186-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="32186-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="32186-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-183">Linux and macOS</span></span> |
| <span data-ttu-id="32186-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-185">Linux and macOS</span></span> |
| <span data-ttu-id="32186-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="32186-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="32186-187">macOS</span><span class="sxs-lookup"><span data-stu-id="32186-187">macOS</span></span> |
| <span data-ttu-id="32186-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="32186-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="32186-190">System.IO</span></span>

| <span data-ttu-id="32186-191">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-191">Member</span></span> | <span data-ttu-id="32186-192">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-193">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-194">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="32186-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="32186-195">System.IO.Pipes</span></span>

| <span data-ttu-id="32186-196">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-196">Member</span></span> | <span data-ttu-id="32186-197">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="32186-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="32186-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="32186-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="32186-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-201">Linux and macOS</span></span> |
| <span data-ttu-id="32186-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="32186-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="32186-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="32186-205">System.Media</span></span>

| <span data-ttu-id="32186-206">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-206">Member</span></span> | <span data-ttu-id="32186-207">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-208">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="32186-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="32186-209">System.Net</span></span>

| <span data-ttu-id="32186-210">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-210">Member</span></span> | <span data-ttu-id="32186-211">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="32186-212">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="32186-213">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-214">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-215">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-216">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-217">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-218">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-219">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-220">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-221">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-222">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="32186-223">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-224">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-225">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-226">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-227">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-228">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="32186-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="32186-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="32186-230">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-230">Member</span></span> | <span data-ttu-id="32186-231">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="32186-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="32186-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="32186-233">System.Net.Sockets</span></span>

| <span data-ttu-id="32186-234">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-234">Member</span></span> | <span data-ttu-id="32186-235">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="32186-236">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="32186-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="32186-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="32186-238">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-238">Member</span></span> | <span data-ttu-id="32186-239">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="32186-240">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="32186-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="32186-241">System.Reflection</span></span>

| <span data-ttu-id="32186-242">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-242">Member</span></span> | <span data-ttu-id="32186-243">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-244">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-245">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-246">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="32186-247">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-248">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-249">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="32186-250">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="32186-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="32186-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="32186-252">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-252">Member</span></span> | <span data-ttu-id="32186-253">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="32186-254">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="32186-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="32186-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="32186-256">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-256">Member</span></span> | <span data-ttu-id="32186-257">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="32186-258">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="32186-259">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="32186-260">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="32186-261">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-262">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="32186-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="32186-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="32186-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="32186-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="32186-266">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-266">Member</span></span> | <span data-ttu-id="32186-267">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="32186-268">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="32186-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="32186-269">System.Security</span></span>

| <span data-ttu-id="32186-270">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-270">Member</span></span> | <span data-ttu-id="32186-271">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="32186-272">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="32186-273">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-274">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="32186-275">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="32186-276">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="32186-277">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="32186-278">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="32186-279">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="32186-280">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="32186-281">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="32186-282">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="32186-283">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="32186-284">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="32186-285">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="32186-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="32186-286">System.Security.Claims</span></span>

| <span data-ttu-id="32186-287">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-287">Member</span></span> | <span data-ttu-id="32186-288">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="32186-289">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-290">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="32186-291">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-292">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-293">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="32186-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="32186-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="32186-295">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-295">Member</span></span> | <span data-ttu-id="32186-296">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-297">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-298">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="32186-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="32186-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="32186-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="32186-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="32186-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="32186-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="32186-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="32186-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="32186-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="32186-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="32186-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="32186-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="32186-311">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-312">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="32186-313">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-314">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-315">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-316">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-317">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="32186-318">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-319">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="32186-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-322">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-323">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="32186-324">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="32186-325">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="32186-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="32186-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="32186-327">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-327">Member</span></span> | <span data-ttu-id="32186-328">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="32186-329">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="32186-330">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="32186-331">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="32186-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="32186-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="32186-333">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-333">Member</span></span> | <span data-ttu-id="32186-334">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-335">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-336">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-337">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-337">All</span></span> |
| <span data-ttu-id="32186-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="32186-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="32186-339">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="32186-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="32186-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="32186-341">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-341">Member</span></span> | <span data-ttu-id="32186-342">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-343">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="32186-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="32186-344">System.Security.Policy</span></span>

| <span data-ttu-id="32186-345">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-345">Member</span></span> | <span data-ttu-id="32186-346">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-347">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="32186-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="32186-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="32186-349">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-349">Member</span></span> | <span data-ttu-id="32186-350">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-351">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="32186-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="32186-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="32186-353">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-353">Member</span></span> | <span data-ttu-id="32186-354">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-355">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="32186-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="32186-356">System.Threading</span></span>

| <span data-ttu-id="32186-357">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-357">Member</span></span> | <span data-ttu-id="32186-358">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-359">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="32186-360">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="32186-361">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="32186-362">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="32186-363">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="32186-364">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="32186-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="32186-365">System.Xml</span></span>

| <span data-ttu-id="32186-366">Miembro</span><span class="sxs-lookup"><span data-stu-id="32186-366">Member</span></span> | <span data-ttu-id="32186-367">Plataforma</span><span class="sxs-lookup"><span data-stu-id="32186-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="32186-368">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="32186-369">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="32186-370">Todas</span><span class="sxs-lookup"><span data-stu-id="32186-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="32186-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="32186-371">See also</span></span>

- [<span data-ttu-id="32186-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="32186-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="32186-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="32186-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="32186-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="32186-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
