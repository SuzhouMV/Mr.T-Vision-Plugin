# 项目代码汇总: Plugin.GrabImage

> 本文档由 DevPilotAI.Toolbox 自动生成，用于 AI 辅助开发、知识库上传或长上下文代码分析。
> 已自动过滤编译产物、缓存目录、IDE 临时文件和部分自动生成文件。
> 若需要修改代码，请优先依据每个代码块上方的“相对路径”定位原始项目文件。

## 1. 项目概览

- 项目名称: `Plugin.GrabImage`
- 项目路径: `D:\CSharpCode\PluginProject\PluginProject\02Plugins\001图像处理\Plugin.GrabImage`
- 生成时间: `2026-10-19 22:50:27`
- 导出文件数: `9`
- 输出策略: `全部允许类型文件`
- 单文件大小限制: `2 MB`
- 包含 Markdown 文档: `False`
- 包含 HTML 文档: `False`
- 导出后自动拆分: `False`
- 拆分容量限制: `2 MB`

### 1.1 导出选项

- 包含项目目录树: `True`
- 包含文件正文: `True`
- 包含文件元信息: `True`
- 跳过空文件: `True`

### 1.2 文件类型统计

- `.config`: `2` 个
- `.cs`: `4` 个
- `.csproj`: `1` 个
- `.xaml`: `2` 个

## 2. 项目结构树

```text
Plugin.GrabImage/
├── Model/
│   └── ImageNameModel.cs
├── Properties/
│   ├── AssemblyInfo.cs
│   └── DesignTimeResources.xaml
├── ViewModels/
│   └── GrabImageViewModel.cs
├── Views/
│   ├── GrabImageView.xaml
│   └── GrabImageView.xaml.cs
├── app.config
├── packages.config
└── Plugin.GrabImage.csproj
```

## 3. 核心代码文件详情

### 文件 1: `Plugin.GrabImage.csproj`

- **相对路径**: `Plugin.GrabImage.csproj`
- **文件类型**: `C# 项目文件`
- **文件大小**: `8.79 KB`
- **概要**: C# 项目配置文件，包含目标框架、依赖包和构建配置

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProjectGuid>{E8592789-8C00-4BD2-9F29-C126AD251F43}</ProjectGuid>
    <OutputType>library</OutputType>
    <RootNamespace>Plugin.GrabImage</RootNamespace>
    <AssemblyName>Plugin.GrabImage</AssemblyName>
    <TargetFrameworkVersion>v4.7.2</TargetFrameworkVersion>
    <FileAlignment>512</FileAlignment>
    <ProjectTypeGuids>{60dc8134-eba5-43b8-bcc9-bb4bc16c2548};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>
    <WarningLevel>4</WarningLevel>
    <Deterministic>true</Deterministic>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>..\..\..\00Exe\Plugins\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>..\..\..\00Exe\Plugins\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Debug|x86'">
    <DebugSymbols>true</DebugSymbols>
    <OutputPath>bin\x86\Debug\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <DebugType>full</DebugType>
    <PlatformTarget>x86</PlatformTarget>
    <LangVersion>7.3</LangVersion>
    <ErrorReport>prompt</ErrorReport>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Release|x86'">
    <OutputPath>bin\x86\Release\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <Optimize>true</Optimize>
    <DebugType>pdbonly</DebugType>
    <PlatformTarget>x86</PlatformTarget>
    <LangVersion>7.3</LangVersion>
    <ErrorReport>prompt</ErrorReport>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="ControlzEx, Version=5.0.0.0, Culture=neutral, PublicKeyToken=69f1c32f803d307e, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\ControlzEx.5.0.2\lib\net462\ControlzEx.dll</HintPath>
    </Reference>
    <Reference Include="EventMgrLib, Version=1.0.0.0, Culture=neutral, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\00Exe\EventMgrLib.dll</HintPath>
    </Reference>
    <Reference Include="halcondotnet, Version=20.11.1.0, Culture=neutral, PublicKeyToken=4973bed59ddbf2b8, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\00Exe\halcondotnet.dll</HintPath>
    </Reference>
    <Reference Include="HandyControl, Version=3.4.0.0, Culture=neutral, PublicKeyToken=45be8712787a1e5b, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\HandyControl.3.4.0\lib\net472\HandyControl.dll</HintPath>
    </Reference>
    <Reference Include="MahApps.Metro, Version=2.0.0.0, Culture=neutral, PublicKeyToken=51482d6f650b2b3f, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\00Exe\MahApps.Metro.dll</HintPath>
    </Reference>
    <Reference Include="Microsoft.WindowsAPICodePack, Version=1.1.0.0, Culture=neutral, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\Microsoft.WindowsAPICodePack-Core.1.1.0.0\lib\Microsoft.WindowsAPICodePack.dll</HintPath>
    </Reference>
    <Reference Include="Microsoft.WindowsAPICodePack.Shell, Version=1.1.0.0, Culture=neutral, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\Microsoft.WindowsAPICodePack-Shell.1.1.0.0\lib\Microsoft.WindowsAPICodePack.Shell.dll</HintPath>
    </Reference>
    <Reference Include="Microsoft.WindowsAPICodePack.ShellExtensions, Version=1.1.0.0, Culture=neutral, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\Microsoft.WindowsAPICodePack-Shell.1.1.0.0\lib\Microsoft.WindowsAPICodePack.ShellExtensions.dll</HintPath>
    </Reference>
    <Reference Include="Microsoft.Xaml.Behaviors, Version=1.1.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL">
      <HintPath>..\..\..\packages\Microsoft.Xaml.Behaviors.Wpf.1.1.31\lib\net45\Microsoft.Xaml.Behaviors.dll</HintPath>
    </Reference>
    <Reference Include="System" />
    <Reference Include="System.ComponentModel.DataAnnotations" />
    <Reference Include="System.Configuration" />
    <Reference Include="System.Data" />
    <Reference Include="System.Web" />
    <Reference Include="System.Web.Extensions" />
    <Reference Include="System.Windows.Forms" />
    <Reference Include="System.Xml" />
    <Reference Include="Microsoft.CSharp" />
    <Reference Include="System.Core" />
    <Reference Include="System.Xml.Linq" />
    <Reference Include="System.Data.DataSetExtensions" />
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Xaml">
      <RequiredTargetFramework>4.0</RequiredTargetFramework>
    </Reference>
    <Reference Include="VM.Halcon, Version=2.1.0.0, Culture=neutral, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\00Exe\VM.Halcon.dll</HintPath>
    </Reference>
    <Reference Include="WindowsBase" />
    <Reference Include="PresentationCore" />
    <Reference Include="PresentationFramework" />
    <Reference Include="WindowsFormsIntegration" />
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Model\ImageNameModel.cs" />
    <Compile Include="Properties\AssemblyInfo.cs">
      <SubType>Code</SubType>
    </Compile>
    <Compile Include="Properties\Resources.Designer.cs">
      <AutoGen>True</AutoGen>
      <DesignTime>True</DesignTime>
      <DependentUpon>Resources.resx</DependentUpon>
    </Compile>
    <Compile Include="Properties\Settings.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Settings.settings</DependentUpon>
      <DesignTimeSharedInput>True</DesignTimeSharedInput>
    </Compile>
    <Compile Include="ViewModels\GrabImageViewModel.cs" />
    <Compile Include="Views\GrabImageView.xaml.cs">
      <DependentUpon>GrabImageView.xaml</DependentUpon>
    </Compile>
    <EmbeddedResource Include="Properties\Resources.resx">
      <Generator>ResXFileCodeGenerator</Generator>
      <LastGenOutput>Resources.Designer.cs</LastGenOutput>
    </EmbeddedResource>
    <None Include="app.config" />
    <None Include="Obfuscar.xml" />
    <None Include="packages.config" />
    <None Include="Properties\Settings.settings">
      <Generator>SettingsSingleFileGenerator</Generator>
      <LastGenOutput>Settings.Designer.cs</LastGenOutput>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Page Include="Properties\DesignTimeResources.xaml">
      <Generator>MSBuild:Compile</Generator>
      <SubType>Designer</SubType>
    </Page>
    <Page Include="Views\GrabImageView.xaml">
      <SubType>Designer</SubType>
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
  <ItemGroup>
    <Resource Include="Assets\Images\Tool\GrabImage.png" />
  </ItemGroup>
  <PropertyGroup>
    <ObfuscarEnabled Condition="'$(ObfuscarEnabled)' == '' and '$(Configuration)' == 'Release'">true</ObfuscarEnabled>
    <ObfuscarEnabled Condition="'$(ObfuscarEnabled)' == ''">false</ObfuscarEnabled>
    <ObfuscarConfigFile>$(ProjectDir)Obfuscar.xml</ObfuscarConfigFile>
    <ObfuscarExe Condition="'$(ObfuscarExe)' == ''">$(MSBuildThisFileDirectory)..\..\..\packages\Obfuscar.2.2.50\tools\Obfuscar.Console.exe</ObfuscarExe>
  </PropertyGroup>
  <Target Name="RunObfuscar" AfterTargets="Build" Condition="'$(Configuration)' == 'Release' and '$(ObfuscarEnabled)' == 'true'">
    <Error Condition="!Exists('$(ObfuscarConfigFile)')" Text="找不到 Obfuscar 配置文件: $(ObfuscarConfigFile)" />
    <Error Condition="!Exists('$(ObfuscarExe)')" Text="找不到 Obfuscar.Console.exe: $(ObfuscarExe)。请确认 Obfuscar 2.2.50 包已还原，或通过 /p:ObfuscarExe=... 指定实际工具路径。" />
    <Exec WorkingDirectory="$(ProjectDir)" Command="&quot;$(ObfuscarExe)&quot; &quot;$(ObfuscarConfigFile)&quot;" />
  </Target>
  <ItemGroup>
    <Reference Include="VM.Start">
      <HintPath>..\..\..\00Exe\VM.Start.exe</HintPath>
    </Reference>
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

---

### 文件 2: `Views/GrabImageView.xaml`

- **相对路径**: `Views/GrabImageView.xaml`
- **文件类型**: `WPF/XAML 文件`
- **文件大小**: `36.92 KB`
- **概要**: WPF/XAML 界面布局或资源定义文件

```xml
﻿<vb:ModuleViewBase 
                   x:Class="Plugin.GrabImage.Views.GrabImageView"
                   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"                                                      
                   xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"    
                   xmlns:vb="clr-namespace:VM.Start.Core;assembly=VM.Start"
                   xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
                   xmlns:mah="http://metro.mahapps.com/winfx/xaml/controls"
                   xmlns:b="http://schemas.microsoft.com/xaml/behaviors"
                   xmlns:helper="clr-namespace:VM.Start.Common.Helper;assembly=VM.Start"
                   xmlns:enum="clr-namespace:VM.Start.Common.Enums;assembly=VM.Start"
                   xmlns:cvt="clr-namespace:VM.Start.Assets.Converter;assembly=VM.Start"
                   xmlns:WinFormHost="clr-namespace:System.Windows.Forms.Integration;assembly=WindowsFormsIntegration"
                   xmlns:hw="clr-namespace:VM.Halcon;assembly=VM.Halcon"                   
                   xmlns:vm="clr-namespace:Plugin.GrabImage.ViewModels"
                   xmlns:local="clr-namespace:Plugin.GrabImage.Views" 
                   Icon="/Plugin.GrabImage;component/Assets/Images/Tool/GrabImage.png"
                   FontFamily="Segoe UI, Microsoft YaHei UI"
                   Background="{DynamicResource WindowBackground}"
                   Height="680" Width="980" Activated="ModuleViewBase_Activated" Loaded="ModuleViewBase_Loaded"
                   >
    <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary>
                    <BooleanToVisibilityConverter x:Key="BooleanToVisibilityConverter"/>
                    <cvt:EnumConverter x:Key="EnumConverter"/>
                    <cvt:EnumToVisibilityConverter x:Key="EnumToVisibilityConverter"/>
                    <cvt:StatusConverter x:Key="StatusConverter"/>
                </ResourceDictionary>
            </ResourceDictionary.MergedDictionaries>

            <Style x:Key="GrabImageFieldLabelStyle"
                  TargetType="{x:Type TextBlock}">
               <Setter Property="Foreground"
                       Value="{DynamicResource TextSecondary}"/>
               <Setter Property="VerticalAlignment" Value="Center"/>
               <Setter Property="Margin" Value="0,0,8,0"/>
            </Style>

            <Style TargetType="{x:Type GroupBox}"
                   BasedOn="{StaticResource MahApps.Styles.GroupBox}">
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="BorderThickness" Value="1"/>
               <Setter Property="Padding" Value="12"/>
               <Setter Property="Margin" Value="0,0,0,10"/>
            </Style>

            <Style TargetType="{x:Type TextBlock}">
               <Setter Property="Foreground"
                       Value="{DynamicResource TextSecondary}"/>
            </Style>

            <Style TargetType="{x:Type CheckBox}"
                   BasedOn="{StaticResource MahApps.Styles.CheckBox}">
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="Margin" Value="0,4,0,6"/>
            </Style>

            <Style TargetType="{x:Type RadioButton}"
                   BasedOn="{StaticResource MahApps.Styles.RadioButton}">
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="Margin" Value="0,3,18,6"/>
            </Style>

            <Style TargetType="{x:Type ComboBox}"
                   BasedOn="{StaticResource MahApps.Styles.ComboBox}">
               <Setter Property="Height" Value="30"/>
               <Setter Property="Padding" Value="8,3"/>
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
            </Style>

            <Style x:Key="GrabImageIconButtonStyle"
                  TargetType="{x:Type Button}"
                  BasedOn="{StaticResource VmButton}">
               <Setter Property="Width" Value="32"/>
               <Setter Property="Height" Value="30"/>
               <Setter Property="Margin" Value="0,0,6,0"/>
               <Setter Property="Padding" Value="0"/>
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
            </Style>

            <Style x:Key="GrabImageDataGridColumnHeaderStyle"
                  TargetType="{x:Type DataGridColumnHeader}"
                  BasedOn="{StaticResource MahApps.Styles.DataGridColumnHeader}">
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="BorderThickness" Value="0,0,0,1"/>
               <Setter Property="FontWeight" Value="SemiBold"/>
               <Setter Property="Padding" Value="8,5"/>
               <Setter Property="HorizontalContentAlignment" Value="Center"/>
            </Style>

            <Style x:Key="GrabImageDataGridRowHeaderStyle"
                  TargetType="{x:Type DataGridRowHeader}"
                  BasedOn="{StaticResource MahApps.Styles.DataGridRowHeader}">
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextSecondary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
            </Style>

            <Style x:Key="GrabImageDataGridCellStyle"
                  TargetType="{x:Type DataGridCell}"
                  BasedOn="{StaticResource MahApps.Styles.DataGridCell}">
               <Setter Property="Background"
                       Value="Transparent"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="Padding" Value="6,3"/>
               <Style.Triggers>
                   <Trigger Property="IsSelected" Value="True">
                       <Setter Property="Background"
                               Value="Transparent"/>
                       <Setter Property="Foreground"
                               Value="{DynamicResource ContentTextPrimary}"/>
                   </Trigger>
               </Style.Triggers>
            </Style>

            <Style x:Key="GrabImageDataGridRowStyle"
                  TargetType="{x:Type DataGridRow}"
                  BasedOn="{StaticResource MahApps.Styles.DataGridRow}">
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackground}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Style.Triggers>
                   <Trigger Property="IsSelected" Value="True">
                       <Setter Property="Background"
                               Value="{DynamicResource Accent}"/>
                       <Setter Property="Foreground"
                               Value="{DynamicResource ContentTextPrimary}"/>
                   </Trigger>
                   <DataTrigger Binding="{Binding IsCurrent}" Value="True">
                       <Setter Property="Background" Value="{DynamicResource AccentHover}"/>
                       <Setter Property="Foreground" Value="{DynamicResource TextSecondary}"/>
                       <Setter Property="FontWeight" Value="Bold"/>
                   </DataTrigger>
                   <MultiDataTrigger>
                       <MultiDataTrigger.Conditions>
                           <Condition Binding="{Binding IsCurrent}" Value="True"/>
                           <Condition Binding="{Binding IsSelected, RelativeSource={RelativeSource Self}}" Value="True"/>
                       </MultiDataTrigger.Conditions>
                       <Setter Property="Background" Value="{DynamicResource Accent}"/>
                       <Setter Property="Foreground" Value="{DynamicResource ContentTextPrimary}"/>
                       <Setter Property="FontWeight" Value="Bold"/>
                   </MultiDataTrigger>
               </Style.Triggers>
            </Style>

            <Style x:Key="GrabImageDataGridStyle"
                  TargetType="{x:Type DataGrid}"
                  BasedOn="{StaticResource MahApps.Styles.DataGrid}">
               <Setter Property="Background"
                       Value="{DynamicResource SurfaceBackground}"/>
               <Setter Property="Foreground"
                       Value="{DynamicResource TextPrimary}"/>
               <Setter Property="BorderBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="RowBackground"
                       Value="{DynamicResource SurfaceBackground}"/>
               <Setter Property="AlternatingRowBackground"
                       Value="{DynamicResource SurfaceBackgroundSecondary}"/>
               <Setter Property="HorizontalGridLinesBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="VerticalGridLinesBrush"
                       Value="{DynamicResource BorderSubtle}"/>
               <Setter Property="GridLinesVisibility" Value="Horizontal"/>
               <Setter Property="ColumnHeaderStyle"
                       Value="{StaticResource GrabImageDataGridColumnHeaderStyle}"/>
               <Setter Property="RowHeaderStyle"
                       Value="{StaticResource GrabImageDataGridRowHeaderStyle}"/>
               <Setter Property="CellStyle"
                       Value="{StaticResource GrabImageDataGridCellStyle}"/>
               <Setter Property="RowStyle"
                       Value="{StaticResource GrabImageDataGridRowStyle}"/>
            </Style>
        </ResourceDictionary>
    </Window.Resources>

    <Grid Background="{DynamicResource WindowBackground}">
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition Height="55"/>
        </Grid.RowDefinitions>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="370"/>
                <ColumnDefinition Width="4"/>
                <ColumnDefinition/>
            </Grid.ColumnDefinitions>
            <TabControl Style="{StaticResource VerTabControl}"
                        Background="{DynamicResource SurfaceBackground}">
                <TabControl.Resources>
                    <Style TargetType="TabItem" BasedOn="{StaticResource VerTabItem}"/>
                </TabControl.Resources>
                <TabItem Header="基本参数">
                    <Grid x:Name="gd">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="*"/>
                        </Grid.RowDefinitions>
                        <Border >
                            <GroupBox Header="采集模式">
                                <StackPanel Orientation="Horizontal" Margin="5 0">
                                    <RadioButton Content="指定图像" Margin="5 0" 
                                                 IsChecked="{Binding ImageSource,Converter={StaticResource EnumConverter},ConverterParameter={x:Static enum:eImageSource.指定图像}}"/>
                                    <RadioButton Content="文件目录" Margin="35 0" 
                                                 IsChecked="{Binding ImageSource,Converter={StaticResource EnumConverter},ConverterParameter={x:Static enum:eImageSource.文件目录}}"/>
                                    <RadioButton Content="相机采集" Margin="5 0" 
                                                 IsChecked="{Binding ImageSource,Converter={StaticResource EnumConverter},ConverterParameter={x:Static enum:eImageSource.相机采集}}"/>
                                </StackPanel>
                            </GroupBox>
                        </Border>
                        <Border x:Name="bd" Grid.Row="1">
                            <GroupBox Header="{Binding ContentHeader}" >
                                <Grid>
                                    <Grid Visibility="{Binding ImageSource,Converter={StaticResource EnumToVisibilityConverter},ConverterParameter={x:Static enum:eImageSource.指定图像}}">
                                        <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
                                            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
                                                <RadioButton Content="选择文件" IsChecked="{Binding SpecifiedImage_SelectFile}"/>
                                                <RadioButton Content="链接路径" Margin="50 0 0 0" IsChecked="{Binding SpecifiedImage_LinkPath}"/>
                                            </StackPanel>
                                            <StackPanel Margin="0 15" Visibility="{Binding SpecifiedImage_SelectFile,Converter={StaticResource BooleanToVisibilityConverter}}">
                                                <TextBox Width="350" Style="{DynamicResource MahApps.Styles.TextBox.Search}" Text="{Binding ImagePath}"
                                                     mah:TextBoxHelper.ButtonCommand="{Binding ImagePathCommand, Mode=OneWay}"/>
                                            </StackPanel>
                                            <StackPanel Margin="0 15" Visibility="{Binding SpecifiedImage_LinkPath,Converter={StaticResource BooleanToVisibilityConverter}}">
                                                <TextBox Width="350" Style="{StaticResource LinkTextBox}" IsReadOnly="True"
                                                         Text="{Binding SpecifiedImagePathLink.Text,Mode=OneWay}"
                                                         mah:TextBoxHelper.LinkButtonCommand="{Binding LinkCommand,Mode=OneWay}"
                                                         mah:TextBoxHelper.LinkButtonCommandParameter="{x:Static vm:eLinkCommand.SpecifiedImagePath}"/>
                                            </StackPanel>
                                        </StackPanel>
                                    </Grid>
                                    <Grid Visibility="{Binding ImageSource,Converter={StaticResource EnumToVisibilityConverter},ConverterParameter={x:Static enum:eImageSource.文件目录}}">
                                        <Grid.RowDefinitions>
                                            <RowDefinition Height="AUTO"/>
                                            <RowDefinition Height="AUTO"/>
                                            <RowDefinition/>
                                        </Grid.RowDefinitions>
                                        <Grid Margin="5 0">
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="Auto"/>
                                                <ColumnDefinition/>
                                            </Grid.ColumnDefinitions>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                                                <CheckBox Content="循环" Margin="0,0,8,0" IsChecked="{Binding IsCyclicRead}"/>
                                                <CheckBox Content="单轮停止" Margin="0,0,8,0" IsChecked="{Binding IsSingleCycleStop}"
                                                          ToolTip="勾选后，循环读取所有勾选图像一次后自动停止并报错"
                                                          Visibility="{Binding IsCyclicRead, Converter={StaticResource BooleanToVisibilityConverter}}"/>
                                            </StackPanel>
                                            <TextBox Grid.Column="1" Style="{DynamicResource MahApps.Styles.TextBox.Search}" Height="25" Text="{Binding FilePath}"
                                                     mah:TextBoxHelper.ButtonCommand="{Binding FilePathCommand, Mode=OneWay}"/>
                                        </Grid>
                                        <DockPanel Grid.Row="1" Margin="5 4" LastChildFill="True">
                                            <StackPanel Orientation="Horizontal" DockPanel.Dock="Left">
                                                <Button Content="全选" Width="36" Height="26" Margin="0,0,3,0"
                                                        Style="{StaticResource VmButton}" FontSize="11"
                                                        Command="{Binding SelectAllCommand}" ToolTip="勾选所有图像"/>
                                                <Button Content="全不" Width="36" Height="26" Margin="0,0,3,0"
                                                        Style="{StaticResource VmButton}" FontSize="11"
                                                        Command="{Binding UnselectAllCommand}" ToolTip="取消勾选所有图像"/>
                                                <Button Content="反选" Width="36" Height="26" Margin="0,0,6,0"
                                                        Style="{StaticResource VmButton}" FontSize="11"
                                                        Command="{Binding InvertSelectCommand}" ToolTip="反转勾选状态"/>
                                                <Button Content="&#xe684;" FontFamily="{DynamicResource iconfont}" FontSize="16"
                                                        Style="{StaticResource GrabImageIconButtonStyle}" ToolTip="上移"
                                                        Command="{Binding MoveUpCommand}"/>
                                                <Button Content="&#xe683;" FontFamily="{DynamicResource iconfont}" FontSize="16"
                                                        Style="{StaticResource GrabImageIconButtonStyle}" ToolTip="下移"
                                                        Command="{Binding MoveDownCommand}"/>
                                                <Button Content="&#xe65e;" FontFamily="{DynamicResource iconfont}" FontSize="16"
                                                        Style="{StaticResource GrabImageIconButtonStyle}" ToolTip="将图片按照时间排序"
                                                        Command="{Binding SortByTimeCommand}"/>
                                                <Button Content="&#xe6fc;" FontFamily="{DynamicResource iconfont}" FontSize="16"
                                                        Style="{StaticResource GrabImageIconButtonStyle}" ToolTip="将图片按照名称排序"
                                                        Command="{Binding SortByNameCommand}"/>
                                            </StackPanel>
                                            <TextBlock DockPanel.Dock="Right" Text="{Binding BatchStatusText}"
                                                       HorizontalAlignment="Right" VerticalAlignment="Center"
                                                       FontSize="11" Foreground="{DynamicResource TextSecondary}" Margin="0,0,4,0"/>
                                        </DockPanel>
                                        <DataGrid Grid.Row="2" Style="{StaticResource GrabImageDataGridStyle}" AutoGenerateColumns="False" x:Name="dg"
                                                  EnableColumnVirtualization="True"
                                                  EnableRowVirtualization="True"
                                                  VirtualizingPanel.IsVirtualizing="True"
                                                  ItemsSource="{Binding ImageNameModels}" SelectedIndex="{Binding SelectedIndex}"
                                                  FontSize="12" 
                                                  RowHeaderWidth="20"
                                                  SelectionUnit="FullRow"
                                                  HeadersVisibility="Column"
                                                  GridLinesVisibility="All"
                                                  IsReadOnly="True" CanUserAddRows="False">
                                            <b:Interaction.Triggers>
                                                <b:EventTrigger EventName="PreviewMouseDoubleClick">
                                                    <helper:EventTriggerAction Command="{Binding PreviewMouseDoubleClick_FilePath}"/>
                                                </b:EventTrigger>
                                            </b:Interaction.Triggers>

                                            <DataGrid.Columns>
                                                <DataGridTemplateColumn Header="" IsReadOnly="True" Width="35">
                                                    <DataGridTemplateColumn.CellTemplate>
                                                        <DataTemplate>
                                                            <CheckBox IsChecked="{Binding IsSelected, UpdateSourceTrigger=PropertyChanged}" VerticalAlignment="Center" Margin="5 0 0 0"/>
                                                        </DataTemplate>
                                                    </DataGridTemplateColumn.CellTemplate>
                                                </DataGridTemplateColumn>
                                                <DataGridTemplateColumn Header="索引" IsReadOnly="True" Width="auto">
                                                    <DataGridTemplateColumn.CellTemplate>
                                                        <DataTemplate>
                                                            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" VerticalAlignment="Center">
                                                                <TextBlock Text="▶" Foreground="{DynamicResource StatusSuccess}" FontSize="10" Margin="0,0,2,0"
                                                                           Visibility="{Binding IsCurrent, Converter={StaticResource BooleanToVisibilityConverter}}"/>
                                                                <TextBlock Text="{Binding ID}" HorizontalAlignment="Center" VerticalAlignment="Center"/>
                                                            </StackPanel>
                                                        </DataTemplate>
                                                    </DataGridTemplateColumn.CellTemplate>
                                                </DataGridTemplateColumn>
                                                <DataGridTemplateColumn Header="名称" IsReadOnly="True" Width="*">
                                                    <DataGridTemplateColumn.CellTemplate>
                                                        <DataTemplate>
                                                            <TextBlock Text="{Binding ImageName}" HorizontalAlignment="Left"/>
                                                        </DataTemplate>
                                                    </DataGridTemplateColumn.CellTemplate>
                                                </DataGridTemplateColumn>
                                            </DataGrid.Columns>
                                        </DataGrid>
                                    </Grid>
                                    <Grid x:Name="gd2" Visibility="{Binding ImageSource,Converter={StaticResource EnumToVisibilityConverter},ConverterParameter={x:Static enum:eImageSource.相机采集}}">
                                        <StackPanel Margin="0 10" HorizontalAlignment="Left">
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="相机选择:" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <ComboBox BorderThickness="0 0 0 1" Width="200" ItemsSource="{Binding CameraModels}" DisplayMemberPath="CameraNo" SelectedItem="{Binding SelectedCameraModel}"/>
                                            </StackPanel>

                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="相机旋转:" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <ComboBox BorderThickness="0 0 0 1" Width="200"/>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="相机备注:" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <Border Width="200" BorderThickness="0 0 0 0.5" BorderBrush="{DynamicResource BorderSubtle}">
                                                    <TextBlock Text=""/>
                                                </Border>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="采集模式:" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <ComboBox Width="200" BorderThickness="0 0 0 1" 
                                                         ItemsSource="{Binding AcquisitionModes}" SelectedItem="{Binding AcquisitionMode}"/>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="曝光时间" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <TextBox Text="{Binding ExposureTime.Value}"
                                                         mah:TextBoxHelper.Value="{Binding ExposureTime.Text}"
                                                         IsReadOnly="{Binding ExposureTime.IsReadOnly}"
                                                         Style="{StaticResource LinkTextBox}"
                                                         mah:TextBoxHelper.LinkButtonCommand="{Binding LinkCommand,Mode=OneWay}"
                                                         mah:TextBoxHelper.Watermark="int"
                                                         mah:TextBoxHelper.LinkButtonCommandParameter="{x:Static vm:eLinkCommand.ExposureTime}"
                                                         VerticalAlignment="Center" HorizontalAlignment="Center" Width="200"  Margin="5 0"/>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <TextBlock Text="增       益" Style="{StaticResource GrabImageFieldLabelStyle}"/>
                                                <TextBox Text="{Binding Gain.Value}"
                                                         mah:TextBoxHelper.Value="{Binding Gain.Text}"
                                                         IsReadOnly="{Binding Gain.IsReadOnly}"
                                                         Style="{StaticResource LinkTextBox}"
                                                         mah:TextBoxHelper.LinkButtonCommand="{Binding LinkCommand,Mode=OneWay}"
                                                         mah:TextBoxHelper.Watermark="int"
                                                         mah:TextBoxHelper.LinkButtonCommandParameter="{x:Static vm:eLinkCommand.Gain}"
                                                         VerticalAlignment="Center" HorizontalAlignment="Center" Width="200"  Margin="5 0"/>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="30 5">
                                                <StackPanel Orientation="Horizontal">
                                                    <TextBlock Text="预处理:" Style="{StaticResource GrabImageFieldLabelStyle}" Margin="10 0 10 0"/>
                                                    <StackPanel Orientation="Horizontal" Margin="0 0 0 0">
                                                        <StackPanel>
                                                            <CheckBox Content="水平镜像" IsChecked="{Binding EnableHorizontalMirror, Mode=TwoWay}"/>
                                                            <CheckBox Content="旋转90°" IsChecked="{Binding Rotate90, Mode=TwoWay}"/>
                                                        </StackPanel>
                                                        <StackPanel>
                                                            <CheckBox Content="垂直镜像" IsChecked="{Binding EnableVerticalMirror, Mode=TwoWay}"/>
                                                            <CheckBox Content="旋转-90°" IsChecked="{Binding RotateMinus90, Mode=TwoWay}"/>
                                                        </StackPanel>
                                                    </StackPanel>
                                                </StackPanel>
                                            </StackPanel>
                                            <StackPanel Orientation="Horizontal">
                                                <GroupBox Header="光源通讯" Width="{Binding ElementName=gd2,Path=ActualWidth}">
                                                    <CheckBox Content="启用光源控制" Margin="10 0"/>
                                                </GroupBox>
                                            </StackPanel>
                                        </StackPanel>
                                    </Grid>
                                </Grid>
                            </GroupBox>
                        </Border>
                    </Grid>

                </TabItem>
                <TabItem Header="图像参数">
                    <Grid x:Name="gd1">
                        <GroupBox Header="图像参数">
                            <StackPanel>
                                <CheckBox Content="流程结束时显示结果图像" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <StackPanel Orientation="Horizontal" Margin="10 10 0 0">
                                    <TextBlock Text="源图像缩放系数" VerticalAlignment="Center"/>
                                    <TextBox Text="{Binding ImageScaleFactor, UpdateSourceTrigger=PropertyChanged}" Width="100" Margin="8 0 0 0"
                                             VerticalAlignment="Center" mah:TextBoxHelper.Watermark="大于0"/>
                                </StackPanel>
                                <StackPanel Orientation="Horizontal" Margin="10">
                                    <TextBlock Text="显示窗体" HorizontalAlignment="Center" VerticalAlignment="Center"/>
                                    <ComboBox HorizontalAlignment="Center" VerticalAlignment="Center" BorderThickness="0 0 0 1" Width="200" Margin="5 0"
                                              SelectedIndex="{Binding DispViewID}" ItemsSource="{Binding CanvasList}"/>
                                </StackPanel>
                                <CheckBox Content="链接测量标定" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="链接拍照位置数据" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="离线图像增加标记" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="链接畸变标定" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="裁剪镭射图像" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="镭射反向扫描" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="手动阈值" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <CheckBox Content="输出亮度图" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="10 10 0 0"/>
                                <Button Content="触发line1" HorizontalAlignment="Left" Margin="10 10 0 0"/>
                            </StackPanel>
                        </GroupBox>
                    </Grid>
                </TabItem>
            </TabControl>
            <GridSplitter Grid.Column="1"
                          Background="{DynamicResource BorderSubtle}"
                          ShowsPreview="True"/>
            <Border Grid.Column="2"
                    Margin="8"
                    Background="#101216"
                    BorderBrush="{DynamicResource BorderSubtle}"
                    BorderThickness="1"
                    CornerRadius="3"
                    ClipToBounds="True">
                <WinFormHost:WindowsFormsHost Margin="1" x:Name="winFormHost"/>
            </Border>

        </Grid>
        <Border Grid.Row="1"
                Background="{DynamicResource SurfaceBackgroundSecondary}"
                BorderBrush="{DynamicResource BorderSubtle}"
                BorderThickness="0 1 0 0">
            <DockPanel LastChildFill="True">
                <StackPanel Margin="10 0 0 0" HorizontalAlignment="Center" VerticalAlignment="Center">
                    <TextBlock>
                        <Run Text="耗时:"/>
                        <Run Text="{Binding ModuleParam.ElapsedTime}"/>
                        <Run Text="ms"/>
                    </TextBlock>
                    <TextBlock>
                        <Run Text="状态:"/>
                        <Run Text="{Binding ModuleParam.Status,Converter={StaticResource StatusConverter}}"/>
                    </TextBlock>
                </StackPanel>
                <StackPanel Orientation="Horizontal" HorizontalAlignment="Right">
                    <Button x:Name="btnExecute" Content="执行" HorizontalAlignment="Right" Margin="10 0"
                            Style="{StaticResource VmButton}"
                            Command="{Binding ExecuteCommand}"/>
                    <Button x:Name="btnCancel" Content="取消" HorizontalAlignment="Right" Margin="10 0"
                            Style="{StaticResource VmButton}"
                            Click="btnCancel_Click"/>
                    <Button x:Name="btnConfirm" Content="确认" HorizontalAlignment="Right" Margin="10 0"
                            Style="{StaticResource VmButton}"
                            Command="{Binding ConfirmCommand}"/>
                </StackPanel>
            </DockPanel>
        </Border>

    </Grid>
</vb:ModuleViewBase>
```

---

### 文件 3: `Model/ImageNameModel.cs`

- **相对路径**: `Model/ImageNameModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `1.52 KB`
- **命名空间**: `Plugin.GrabImage.Model`
- **核心类型**: `class ImageNameModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

```csharp
﻿using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using VM.Start.Common.Helper;

namespace Plugin.GrabImage.Model
{
    [Serializable]
    public class ImageNameModel:NotifyPropertyBase
    {
        private int _ID;
        /// <summary>
        /// ID
        /// </summary>
        public int ID
        {
            get { return _ID; }
            set { Set(ref _ID, value); }
        }
        private bool _IsSelected;
        /// <summary>
        /// 是否选中
        /// </summary>
        public bool IsSelected
        {
            get { return _IsSelected; }
            set { Set(ref _IsSelected, value); }
        }
        private string _ImageName;
        /// <summary>
        /// 图片名称
        /// </summary>
        public string ImageName
        {
            get { return _ImageName; }
            set { Set(ref _ImageName, value); }
        }
        private string _ImagePath;
        /// <summary>
        /// 图片路径
        /// </summary>
        public string ImagePath
        {
            get { return _ImagePath; }
            set { Set(ref _ImagePath, value); }
        }

        [NonSerialized]
        private bool _IsCurrent;
        /// <summary>
        /// 是否为当前正在执行/加载的图像
        /// </summary>
        public bool IsCurrent
        {
            get { return _IsCurrent; }
            set { Set(ref _IsCurrent, value); }
        }

    }
}
```

---

### 文件 4: `Properties/AssemblyInfo.cs`

- **相对路径**: `Properties/AssemblyInfo.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `2.23 KB`
- **命名空间**: ``
- **核心类型**: `未识别`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: C# 源码文件，未识别到明确的类型定义

```csharp
﻿using System.Reflection;
using System.Resources;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;
using System.Windows;

// 有关程序集的一般信息由以下
// 控制。更改这些特性值可修改
// 与程序集关联的信息。
[assembly: AssemblyTitle("Plugin.GrabImage")]
[assembly: AssemblyDescription("")]
[assembly: AssemblyConfiguration("")]
[assembly: AssemblyCompany("")]
[assembly: AssemblyProduct("Plugin.GrabImage")]
[assembly: AssemblyCopyright("Copyright ©  2026")]
[assembly: AssemblyTrademark("")]
[assembly: AssemblyCulture("")]

// 将 ComVisible 设置为 false 会使此程序集中的类型
//对 COM 组件不可见。如果需要从 COM 访问此程序集中的类型
//请将此类型的 ComVisible 特性设置为 true。
[assembly: ComVisible(false)]

//若要开始生成可本地化的应用程序，请设置
//.csproj 文件中的 <UICulture>CultureYouAreCodingWith</UICulture>
//例如，如果您在源文件中使用的是美国英语，
//使用的是美国英语，请将 <UICulture> 设置为 en-US。  然后取消
//对以下 NeutralResourceLanguage 特性的注释。  更新
//以下行中的“en-US”以匹配项目文件中的 UICulture 设置。

//[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]


[assembly:ThemeInfo(
    ResourceDictionaryLocation.None, //主题特定资源词典所处位置
                             //(未在页面中找到资源时使用，
                             //或应用程序资源字典中找到时使用)
    ResourceDictionaryLocation.SourceAssembly //常规资源词典所处位置
                                      //(未在页面中找到资源时使用，
                                      //、应用程序或任何主题专用资源字典中找到时使用)
)]


// 程序集的版本信息由下列四个值组成: 
//
//      主版本
//      次版本
//      生成号
//      修订号
//
//可以指定所有这些值，也可以使用“生成号”和“修订号”的默认值
//通过使用 "*"，如下所示:
// [assembly: AssemblyVersion("1.0.*")]
[assembly: AssemblyVersion("2.0.0.0")]
[assembly: AssemblyFileVersion("2.0.0.0")]
```

---

### 文件 5: `ViewModels/GrabImageViewModel.cs`

- **相对路径**: `ViewModels/GrabImageViewModel.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `56.38 KB`
- **命名空间**: `Plugin.GrabImage.ViewModels`
- **核心类型**: `enum public`, `enum eLinkCommand`, `class GrabImageViewModel`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 枚举定义文件

```csharp
﻿using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using VM.Start.Core;
using VM.Start.Attributes;
using VM.Start.Common.Const;
using VM.Start.Common.Provide;
using System.Windows.Controls;
using System.Windows.Input;
using VM.Start.Common.Helper;
using VM.Start.Common.Enums;
using HalconDotNet;
using Plugin.GrabImage.Views;
using Microsoft.Win32;
using System.Collections.ObjectModel;
using Plugin.GrabImage.Model;
using System.Windows.Forms;
using System.IO;
using System.Threading;
using System.Windows;
using Microsoft.WindowsAPICodePack.Dialogs;
using VM.Start.Views.Dock;
using VM.Halcon;
using VM.Start.Services;
using VM.Halcon.Config;
using HandyControl.Controls;
using VM.Halcon.Model;
using VM.Start.Views;
using VM.Start.Models;
using VM.Start.ViewModels;
using VM.Start.Events;
using VM.Start.Common;
using System.Windows.Threading;
using EventMgrLib;
using System.Runtime.Serialization;

namespace Plugin.GrabImage.ViewModels
{
    #region enum
    public enum eLinkCommand
    {
        ExposureTime,
        Gain,
        SpecifiedImagePath
    }

    #endregion

    [Category("图像处理")]
    [DisplayName("采集图像")]
    [ModuleImageName("GrabImage")]
    [PluginCapability(PluginCapabilities.AsyncExecution | PluginCapabilities.CancelableExecution, PluginVersion = "2.0.0")]
    [Serializable]
    public class GrabImageViewModel : ModuleBase
    {
        private const int WaitSliceMs = 50;

        [NonSerialized]
        private bool _isEditorPreviewExecution;

        [NonSerialized]
        private int _currentCheckedIndex;

        [NonSerialized]
        private bool _batchCycleFinished;

        [NonSerialized]
        private bool _isInternalSelectionUpdate;

        [NonSerialized]
        private int _executionGate;

        [NonSerialized]
        private RImage _editorPreviewImage;

        [NonSerialized]
        private SubscriptionToken _varChangedToken;

        private RImage LoadImageToDisplayBuffer(string imagePath)
        {
            if (string.IsNullOrWhiteSpace(imagePath) || !File.Exists(imagePath))
            {
                return null;
            }

            RImage image = new RImage(DispViewID);
            try
            {
                image.ReadImage(imagePath);
                if (!image.IsInitialized())
                {
                    image.Dispose();
                    return null;
                }

                return image;
            }
            catch
            {
                image.Dispose();
                throw;
            }
        }
        
        private RImage ApplyImageScale(RImage image)
        {
            if (image == null || !image.IsInitialized() || Math.Abs(ImageScaleFactor - 1.0) < 0.000001)
            {
                return image;
            }

            HObject scaledObject = null;
            try
            {
                HOperatorSet.ZoomImageFactor(
                    image,
                    out scaledObject,
                    ImageScaleFactor,
                    ImageScaleFactor,
                    "bilinear");

                return new RImage(scaledObject)
                {
                    DispViewID = DispViewID
                };
            }
            finally
            {
                if (scaledObject != null)
                {
                    scaledObject.Dispose();
                }
            }
        }

        private RImage ApplyImageTransform(RImage image)
        {
            if (image == null || !image.IsInitialized())
            {
                return image;
            }

            HImage transformedImage = null;
            try
            {
                HImage currentImage = image;
                if (EnableHorizontalMirror)
                {
                    transformedImage = currentImage.MirrorImage("column");
                    currentImage = transformedImage;
                }

                if (EnableVerticalMirror)
                {
                    var nextImage = currentImage.MirrorImage("row");
                    if (transformedImage != null)
                    {
                        transformedImage.Dispose();
                    }
                    transformedImage = nextImage;
                    currentImage = transformedImage;
                }

                if (Rotate90 == RotateMinus90)
                {
                    if (Rotate90)
                    {
                        var nextImage = currentImage.RotateImage(180.0, "constant");
                        if (transformedImage != null)
                        {
                            transformedImage.Dispose();
                        }
                        transformedImage = nextImage;
                        currentImage = transformedImage;
                    }
                }
                else
                {
                    var nextImage = currentImage.RotateImage(Rotate90 ? 90.0 : -90.0, "constant");
                    if (transformedImage != null)
                    {
                        transformedImage.Dispose();
                    }
                    transformedImage = nextImage;
                    currentImage = transformedImage;
                }

                if (transformedImage == null)
                {
                    return image;
                }

                return new RImage(transformedImage)
                {
                    DispViewID = DispViewID
                };
            }
            finally
            {
                if (transformedImage != null)
                {
                    transformedImage.Dispose();
                }
            }
        }

        private CameraBase ResolveRuntimeCamera()
        {
            try
            {
                var selected = SelectedCameraModel;
                if (selected == null) return null;

                var cameras = CameraSetViewModel.Ins?.CameraModels;
                if (cameras == null || cameras.Count == 0) return selected;

                // Old solutions may deserialize a stale CameraBase instance into SelectedCameraModel.
                // Prefer the runtime instance from CameraSetViewModel so Connected/device state is correct.
                CameraBase runtime = null;

                if (!string.IsNullOrWhiteSpace(selected.CameraNo))
                {
                    runtime = cameras.FirstOrDefault(c => string.Equals(c?.CameraNo, selected.CameraNo, StringComparison.OrdinalIgnoreCase));
                }

                if (runtime == null && !string.IsNullOrWhiteSpace(selected.SerialNo))
                {
                    runtime = cameras.FirstOrDefault(c => string.Equals(c?.SerialNo, selected.SerialNo, StringComparison.OrdinalIgnoreCase));
                }

                if (runtime != null)
                {
                    if (!ReferenceEquals(runtime, selected))
                    {
                        SelectedCameraModel = runtime;
                    }
                    return runtime;
                }

                return selected;
            }
            catch
            {
                return SelectedCameraModel;
            }
        }

        private bool WaitForCameraImage(CameraBase camera)
        {
            if (camera?.EventWait == null)
            {
                Logger.AddLog(ModuleParam.ModuleName + ":相机未提供采集等待句柄!", eMsgType.Error);
                return false;
            }

            int timeoutMs = TimeOut > 0 ? TimeOut : 5000;
            int waitedMs = 0;

            while (waitedMs < timeoutMs)
            {
                if (CancelWait || (!_isEditorPreviewExecution && (Prj == null || !Prj.ThreadStatus)))
                {
                    Logger.AddLog(ModuleParam.ModuleName + ":采集已取消!", eMsgType.Warn);
                    return false;
                }

                int slice = Math.Min(WaitSliceMs, timeoutMs - waitedMs);
                if (camera.EventWait.WaitOne(slice))
                {
                    return true;
                }

                waitedMs += slice;
            }

            Logger.AddLog(ModuleParam.ModuleName + ":采集图像超时!", eMsgType.Error);
            return false;
        }

        private void UpdateDisplayAsync(RImage image)
        {
            if (image == null || !image.IsInitialized())
            {
                return;
            }

            if (_isEditorPreviewExecution)
            {
                ShowEditorPreview(image);
                return;
            }

            var frame = CreateDisplayFrame();
            frame.BackgroundImage = new HImage(image);
            PublishDisplayFrame(frame);
        }

        private bool ExecuteForEditorPreview()
        {
            _isEditorPreviewExecution = true;
            try
            {
                _batchCycleFinished = false;
                return ExeModule();
            }
            finally
            {
                _isEditorPreviewExecution = false;
            }
        }

        private void UpdatePreviewForSelectedRow()
        {
            if (ImageNameModels == null || SelectedIndex < 0 || SelectedIndex >= ImageNameModels.Count)
            {
                return;
            }

            var item = ImageNameModels[SelectedIndex];
            if (item != null && !string.IsNullOrWhiteSpace(item.ImagePath) && File.Exists(item.ImagePath))
            {
                var img = LoadImageToDisplayBuffer(item.ImagePath);
                if (img != null && img.IsInitialized())
                {
                    ReplaceEditorPreviewImage(img);
                    ShowEditorPreview(_editorPreviewImage);
                }
            }
        }

        private void ReplaceEditorPreviewImage(RImage image)
        {
            RImage previousPreviewImage = _editorPreviewImage;
            _editorPreviewImage = image;
            if (previousPreviewImage != null && !ReferenceEquals(previousPreviewImage, image))
            {
                previousPreviewImage.Dispose();
            }
        }

        private void ScrollToCurrentItem(int index)
        {
            var view = ModuleView as GrabImageView;
            if (view == null || view.IsClosed || view.dg == null)
            {
                return;
            }

            view.Dispatcher.BeginInvoke(new Action(() =>
            {
                try
                {
                    if (!view.IsClosed && view.dg != null && index >= 0 && index < view.dg.Items.Count)
                    {
                        view.dg.ScrollIntoView(view.dg.Items[index]);
                    }
                }
                catch { }
            }));
        }

        private void ShowEditorPreview(RImage image)
        {
            if (image == null || !image.IsInitialized())
            {
                return;
            }

            var view = ModuleView as GrabImageView;
            if (view == null || view.IsClosed || view.mWindowH == null)
            {
                return;
            }

            if (view.Dispatcher.CheckAccess())
            {
                view.DisplayImage(image);
            }
            else
            {
                view.Dispatcher.BeginInvoke(new Action(() =>
                {
                    if (!view.IsClosed && view.mWindowH != null)
                    {
                        try
                        {
                            view.DisplayImage(image);
                        }
                        catch (Exception ex)
                        {
                            Logger.AddLog(
                                ModuleParam.ModuleName + ":插件预览刷新失败:" + ex.Message,
                                eMsgType.Error);
                        }
                    }
                }));
            }
        }

        private void ClearEditorPreview()
        {
            var view = ModuleView as GrabImageView;
            if (view == null || view.IsClosed || view.mWindowH == null)
            {
                return;
            }

            Action clear = () =>
            {
                if (!view.IsClosed && view.mWindowH != null)
                {
                    view.ClearDisplay();
                }
            };

            if (view.Dispatcher.CheckAccess())
            {
                clear();
            }
            else
            {
                view.Dispatcher.BeginInvoke(clear);
            }
        }

        private void ClearDisplay()
        {
            var frame = CreateDisplayFrame();
            PublishDisplayFrame(frame);
            ClearEditorPreview();
        }

        public override Task<bool> ExeModuleAsync(CancellationToken cancellationToken = default(CancellationToken))
        {
            if (!cancellationToken.CanBeCanceled)
            {
                return Task.FromResult(ExeModule());
            }

            return Task.Run(
                () =>
                {
                    using (cancellationToken.Register(() => CancelWait = true))
                    {
                        cancellationToken.ThrowIfCancellationRequested();
                        return ExeModule();
                    }
                },
                cancellationToken);
        }

        public override bool ExeModule()
        {
            if (Interlocked.Exchange(ref _executionGate, 1) != 0)
            {
                Logger.AddLog(ModuleParam.ModuleName + ":已有采集执行正在进行，忽略重复执行请求!", eMsgType.Warn);
                return false;
            }

            Stopwatch.Restart();
            CancelWait = false;
            ClearDisplay();
            RImage previousImage = DispImage;
            DispImage = null;
            RImage nextImage = null;
            try
            {
                CurrentImagePath = string.Empty;
                FrameId = string.Empty;
                switch (ImageSource)
                {
                    case eImageSource.指定图像:
                        string specifiedImagePath = ImagePath;
                        if (SpecifiedImage_LinkPath)
                        {
                            if (SpecifiedImagePathLink == null
                                || string.IsNullOrWhiteSpace(SpecifiedImagePathLink.Text))
                            {
                                Logger.AddLog(ModuleParam.ModuleName + ":链接图像路径为空!", eMsgType.Error);
                                break;
                            }

                            object linkedPath = GetLinkValue(SpecifiedImagePathLink);
                            specifiedImagePath = linkedPath as string
                                ?? Convert.ToString(linkedPath);
                        }

                        nextImage = LoadImageToDisplayBuffer(specifiedImagePath);
                        if (nextImage != null && nextImage.IsInitialized() && !string.IsNullOrWhiteSpace(specifiedImagePath))
                        {
                            CurrentImagePath = Path.GetFullPath(specifiedImagePath);
                        }
                        break;
                    case eImageSource.文件目录:
                        if (ImageNameModels == null || ImageNameModels.Count == 0)
                        {
                            Logger.AddLog(ModuleParam.ModuleName + ":图像列表为空!", eMsgType.Warn);
                            break;
                        }

                        var checkedList = ImageNameModels.Where(x => x.IsSelected).ToList();
                        if (checkedList.Count == 0)
                        {
                            Logger.AddLog(ModuleParam.ModuleName + ":未勾选任何测试图像，批测无法执行!", eMsgType.Error);
                            ChangeModuleRunStatus(eRunStatus.NG);
                            DisposeReplacedImage(previousImage);
                            Prj?.Stop("未勾选测试图像");
                            return false;
                        }

                        if (IsCyclicRead)
                        {
                            if (IsSingleCycleStop && _batchCycleFinished)
                            {
                                Logger.AddLog($"[{ModuleParam.ModuleName}] 文件夹勾选图像（共 {checkedList.Count} 张）已完成单轮测试，批测结束！", eMsgType.Error);
                                ChangeModuleRunStatus(eRunStatus.NG);
                                Prj?.Stop("批量图像单轮测试完成");
                                _batchCycleFinished = false;
                                _currentCheckedIndex = 0;
                                DisposeReplacedImage(previousImage);
                                return false;
                            }

                            if (_currentCheckedIndex >= checkedList.Count)
                            {
                                _currentCheckedIndex = 0;
                            }

                            var targetModel = checkedList[_currentCheckedIndex];

                            if (_currentCheckedIndex == checkedList.Count - 1)
                            {
                                if (IsSingleCycleStop)
                                {
                                    _batchCycleFinished = true;
                                }
                                _currentCheckedIndex = 0;
                            }
                            else
                            {
                                _currentCheckedIndex++;
                            }

                            _isInternalSelectionUpdate = true;
                            try
                            {
                                foreach (var item in ImageNameModels)
                                {
                                    item.IsCurrent = ReferenceEquals(item, targetModel);
                                }
                                SelectedIndex = ImageNameModels.IndexOf(targetModel);
                            }
                            finally
                            {
                                _isInternalSelectionUpdate = false;
                            }

                            ScrollToCurrentItem(SelectedIndex);

                            if (targetModel != null && !string.IsNullOrWhiteSpace(targetModel.ImagePath))
                            {
                                var imagePath = Path.GetFullPath(targetModel.ImagePath);
                                nextImage = LoadImageToDisplayBuffer(imagePath);
                                if (nextImage != null && nextImage.IsInitialized())
                                {
                                    CurrentImagePath = imagePath;
                                }
                            }
                        }
                        else
                        {
                            ImageNameModel targetModel = null;
                            if (SelectedIndex >= 0 && SelectedIndex < ImageNameModels.Count)
                            {
                                targetModel = ImageNameModels[SelectedIndex];
                            }
                            else
                            {
                                targetModel = checkedList[0];
                                _isInternalSelectionUpdate = true;
                                try
                                {
                                    SelectedIndex = ImageNameModels.IndexOf(targetModel);
                                }
                                finally
                                {
                                    _isInternalSelectionUpdate = false;
                                }
                            }

                            if (targetModel != null)
                            {
                                foreach (var item in ImageNameModels)
                                {
                                    item.IsCurrent = ReferenceEquals(item, targetModel);
                                }
                                ScrollToCurrentItem(SelectedIndex);

                                if (!string.IsNullOrWhiteSpace(targetModel.ImagePath))
                                {
                                    var imagePath = Path.GetFullPath(targetModel.ImagePath);
                                    nextImage = LoadImageToDisplayBuffer(imagePath);
                                    if (nextImage != null && nextImage.IsInitialized())
                                    {
                                        CurrentImagePath = imagePath;
                                    }
                                }
                            }
                        }

                        break;
                    case eImageSource.相机采集:
                        var cam = ResolveRuntimeCamera();
                        if (cam == null)
                        {
                            Logger.AddLog(ModuleParam.ModuleName + ":未选择相机!", eMsgType.Warn);
                            break;
                        }

                        if (!cam.Connected)
                        {
                            try
                            {
                                cam.ConnectDev();
                            }
                            catch (Exception ex)
                            {
                                Logger.GetExceptionMsg(ex);
                            }
                        }

                        if (cam.Connected)
                        {
                            try
                            {
                                if (int.TryParse((ExposureTime?.Value ?? ExposureTime?.Text)?.ToString(), out var exp))
                                {
                                    cam.ExposeTime = exp;
                                    cam.SetExposureTime(cam.ExposeTime);
                                }

                                if (int.TryParse((Gain?.Value ?? Gain?.Text)?.ToString(), out var gain))
                                {
                                    cam.Gain = gain;
                                    cam.SetGain(cam.Gain);
                                }

                                if (AcquisitionMode == eTrigMode.下降沿)
                                {
                                    cam.TrigMode = eTrigMode.下降沿;
                                    cam.SetTriggerMode(eTrigMode.下降沿);
                                }
                                else if (AcquisitionMode == eTrigMode.上升沿)
                                {
                                    cam.TrigMode = eTrigMode.上升沿;
                                    cam.SetTriggerMode(eTrigMode.上升沿);
                                }
                                else
                                {
                                    cam.TrigMode = eTrigMode.软触发;
                                    cam.SetTriggerMode(eTrigMode.软触发);
                                }

                                cam.EventWait.Reset();
                                cam.CaptureImage(false);

                                if (!WaitForCameraImage(cam))
                                {
                                    break;
                                }

                                if (cam.Image != null && cam.Image.IsInitialized())
                                {
                                    nextImage = new RImage(cam.Image);
                                    nextImage.DispViewID = DispViewID;
                                }
                            }
                            finally
                            {
                                cam.TrigMode = eTrigMode.软触发;
                                cam.SetTriggerMode(eTrigMode.软触发);
                            }
                        }
                        else
                        {
                            Logger.AddLog(ModuleParam.ModuleName + ":" + (cam.CameraNo ?? "") + "相机未连接!", eMsgType.Warn);
                            //ChangeModuleRunStatus(eRunStatus.NG);
                        }
                        break;
                    default:
                        break;
                }

                if (nextImage != null && nextImage.IsInitialized())
                {
                    var transformedImage = ApplyImageTransform(nextImage);
                    if (!ReferenceEquals(transformedImage, nextImage))
                    {
                        nextImage.Dispose();
                        nextImage = transformedImage;
                    }

                    var scaledImage = ApplyImageScale(nextImage);
                    if (!ReferenceEquals(scaledImage, nextImage))
                    {
                        nextImage.Dispose();
                        nextImage = scaledImage;
                    }
                    if (!ReferenceEquals(DispImage, nextImage) && DispImage != null && DispImage.IsInitialized())
                    {
                        DispImage.Dispose();
                    }

                    DispImage = nextImage;
                    nextImage = null;
                    FrameId = Guid.NewGuid().ToString("N");
                    UpdateDisplayAsync(DispImage);

                    ChangeModuleRunStatus(eRunStatus.OK);
                    DisposeReplacedImage(previousImage);
                    return true;
                }
                else
                {
                    ChangeModuleRunStatus(eRunStatus.NG);
                    ClearCurrentImageAfterFailure();
                    DisposeReplacedImage(previousImage);
                    return false;
                }

            }
            catch (OperationCanceledException)
            {
                ClearCurrentImageAfterFailure();
                ChangeModuleRunStatus(eRunStatus.NG);
                DisposeReplacedImage(previousImage);
                return false;
            }
            catch (Exception ex)
            {
                ClearCurrentImageAfterFailure();
                ChangeModuleRunStatus(eRunStatus.NG);
                DisposeReplacedImage(previousImage);
                Logger.GetExceptionMsg(ex);
                return false;
            }
            finally
            {
                nextImage?.Dispose();
                Volatile.Write(ref _executionGate, 0);
            }
        }

        private void DisposeReplacedImage(RImage previousImage)
        {
            if (previousImage != null && !ReferenceEquals(previousImage, DispImage))
            {
                previousImage.Dispose();
            }
        }

        private void ClearCurrentImageAfterFailure()
        {
            RImage failedImage = DispImage;
            DispImage = null;
            failedImage?.Dispose();
            RImage previewImage = _editorPreviewImage;
            _editorPreviewImage = null;
            previewImage?.Dispose();
            ClearDisplay();
        }

        public override void AddOutputParams()
        {
            base.AddOutputParams();
            AddOutputParam(
                "图像",
                VariableTypes.Image,
                ModuleParam.Status == eRunStatus.OK ? DispImage : null);
            AddOutputParam("图像路径", VariableTypes.String, CurrentImagePath ?? string.Empty);
            AddOutputParam("FrameId", VariableTypes.String, FrameId ?? string.Empty);
        }
        #region Prop
        /// <summary>图像索引</summary>
        public int _SelectedIndex = 0;
        public int SelectedIndex
        {
            get { return _SelectedIndex; }
            set
            {
                Set(ref _SelectedIndex, value, new Action(() =>
                {
                    if (!_isInternalSelectionUpdate && ImageSource == eImageSource.文件目录)
                    {
                        UpdatePreviewForSelectedRow();
                    }
                }));
            }
        }

        private bool _IsCyclicRead = true;
        /// <summary>
        /// 循环读取
        /// </summary>
        public bool IsCyclicRead
        {
            get { return _IsCyclicRead; }
            set
            {
                Set(ref _IsCyclicRead, value);
            }
        }

        [OptionalField]
        private bool _IsSingleCycleStop = true;
        /// <summary>
        /// 循环执行时单轮结束自动停止并报错
        /// </summary>
        public bool IsSingleCycleStop
        {
            get { return _IsSingleCycleStop; }
            set
            {
                Set(ref _IsSingleCycleStop, value);
            }
        }

        [NonSerialized]
        private string _BatchStatusText = string.Empty;
        /// <summary>
        /// 批测进度统计文本
        /// </summary>
        public string BatchStatusText
        {
            get { return _BatchStatusText; }
            set { Set(ref _BatchStatusText, value); }
        }
        private string _ImagePath;
        /// <summary>
        /// 图片路径
        /// </summary>
        public string ImagePath
        {
            get { return _ImagePath; }
            set { _ImagePath = value; RaisePropertyChanged(); }
        }
        private string _FilePath;
        /// <summary>
        /// 图片文件夹路径
        /// </summary>
        public string FilePath
        {
            get { return _FilePath; }
            set { _FilePath = value; RaisePropertyChanged(); }
        }

        private string _CurrentImagePath = string.Empty;
        private string _FrameId = string.Empty;
        public string CurrentImagePath
        {
            get { return _CurrentImagePath; }
            private set { Set(ref _CurrentImagePath, value); }
        }

        public string FrameId
        {
            get { return _FrameId ?? string.Empty; }
            private set { Set(ref _FrameId, value ?? string.Empty); }
        }

        public override void DeleteModule()
        {
            if (_varChangedToken != null)
            {
                EventMgr.Ins.GetEvent<VarChangedEvent>().Unsubscribe(_varChangedToken);
                _varChangedToken = null;
            }

            RImage image = DispImage;
            DispImage = null;
            image?.Dispose();
            RImage previewImage = _editorPreviewImage;
            _editorPreviewImage = null;
            previewImage?.Dispose();
            base.DeleteModule();
        }

        private double _ImageScaleFactor = 1.0;
        public double ImageScaleFactor
        {
            get { return _ImageScaleFactor; }
            set
            {
                if (double.IsNaN(value) || double.IsInfinity(value) || value <= 0)
                {
                    Logger.AddLog(ModuleParam.ModuleName + ":图像缩放系数必须大于0。", eMsgType.Warn);
                    return;
                }

                Set(ref _ImageScaleFactor, value);
            }
        }

        private bool _EnableHorizontalMirror;
        public bool EnableHorizontalMirror
        {
            get { return _EnableHorizontalMirror; }
            set { Set(ref _EnableHorizontalMirror, value); }
        }

        private bool _EnableVerticalMirror;
        public bool EnableVerticalMirror
        {
            get { return _EnableVerticalMirror; }
            set { Set(ref _EnableVerticalMirror, value); }
        }

        private bool _Rotate90;
        public bool Rotate90
        {
            get { return _Rotate90; }
            set { Set(ref _Rotate90, value); }
        }

        private bool _RotateMinus90;
        public bool RotateMinus90
        {
            get { return _RotateMinus90; }
            set { Set(ref _RotateMinus90, value); }
        }
        public List<string> CanvasList
        {
            get { return base.CanvasList; }
            set { base.CanvasList = value; RaisePropertyChanged(); }
        }
        public int DispViewID
        {
            get { return base.DispViewID; }
            set { base.DispViewID = value; RaisePropertyChanged(); }
        }
        /// <summary>
        /// 采集魔术数据,用来显示列表数据源
        /// </summary>

        [field: NonSerialized]
        public Array AcquisitionModes
        {
            get { return Enum.GetValues(typeof(eTrigMode)); }
            set {; }
        }
        /// <summary>
        /// 当前采集模式
        /// </summary>
        private eTrigMode _AcquisitionMode = eTrigMode.软触发;
        public eTrigMode AcquisitionMode
        {
            get { return _AcquisitionMode; }
            set
            {
                Set(ref _AcquisitionMode, value, new Action(() =>
                {
                }));
            }
        }
        /// <summary>
        /// 曝光时间
        /// </summary>
        private LinkVarModel _ExposureTime = new LinkVarModel() { Text = "10000" };
        public LinkVarModel ExposureTime
        {
            get { return _ExposureTime; }
            set { _ExposureTime = value; RaisePropertyChanged(); }
        }

        /// <summary>
        /// 增益
        /// </summary>
        private LinkVarModel _Gain = new LinkVarModel() { Text = "0" };

        public LinkVarModel Gain
        {
            get { return _Gain; }
            set { _Gain = value; RaisePropertyChanged(); }
        }

        private LinkVarModel _SpecifiedImagePathLink = new LinkVarModel();
        public LinkVarModel SpecifiedImagePathLink
        {
            get
            {
                if (_SpecifiedImagePathLink == null)
                {
                    _SpecifiedImagePathLink = new LinkVarModel();
                }

                return _SpecifiedImagePathLink;
            }
            set
            {
                _SpecifiedImagePathLink = value;
                RaisePropertyChanged();
            }
        }


        private string _ContentHeader ="文件目录";
        /// <summary>
        /// 内容标题
        /// </summary>
        public string ContentHeader
        {
            get { return _ContentHeader; }
            set { _ContentHeader = value; RaisePropertyChanged(); }
        }

        private eImageSource _ImageSource = eImageSource.指定图像;
        /// <summary>
        /// 指定图像
        /// </summary>
        public eImageSource ImageSource
        {
            get { return _ImageSource; }
            set
            {
                Set(ref _ImageSource, value, new Action(() =>
                {
                    switch (_ImageSource)
                    {
                        case eImageSource.指定图像:
                            ContentHeader = "指定图像";
                            break;
                        case eImageSource.文件目录:
                            ContentHeader = "文件目录";
                            break;
                        case eImageSource.相机采集:
                            ContentHeader = "相机采集";
                            break;
                        default:
                            break;
                    }
                }));
            }
        }
        private bool _SpecifiedImage_SelectFile = true;
        /// <summary>
        /// 选择文件
        /// </summary>
        public bool SpecifiedImage_SelectFile
        {
            get { return _SpecifiedImage_SelectFile; }
            set
            {
                Set(ref _SpecifiedImage_SelectFile, value);
            }
        }
        private bool _SpecifiedImage_LinkPath;
        /// <summary>
        /// 链接路径
        /// </summary>
        public bool SpecifiedImage_LinkPath
        {
            get { return _SpecifiedImage_LinkPath; }
            set
            {
                Set(ref _SpecifiedImage_LinkPath, value);
            }
        }
        public ObservableCollection<ImageNameModel> ImageNameModels { get; set; }=new ObservableCollection<ImageNameModel>();
        /// <summary>相机列表</summary>
        public ObservableCollection<CameraBase> CameraModels { get; set; } = CameraSetViewModel.Ins.CameraModels;
        private CameraBase _SelectedCameraModel = new CameraBase();

        public CameraBase SelectedCameraModel
        {
            get { return _SelectedCameraModel; }
            set { _SelectedCameraModel = value; RaisePropertyChanged(); }
        }

        #endregion

        #region Command
        public override void Loaded()
        {
            base.Loaded();
            HookItemPropertyChanged();
            UpdateBatchStatusText();
            var view = ModuleView as GrabImageView;
            if (view != null)
            {
                if (view.mWindowH == null)
                {
                    view.mWindowH = new VMHWindowControl();
                    view.winFormHost.Child = view.mWindowH;
                }
            }
        }

        [OnDeserialized]
        private void OnDeserialized(StreamingContext context)
        {
            if (ImageNameModels == null)
            {
                ImageNameModels = new ObservableCollection<ImageNameModel>();
            }

            if (SelectedCameraModel == null)
            {
                SelectedCameraModel = new CameraBase();
            }

            if (_ExposureTime == null)
            {
                _ExposureTime = new LinkVarModel { Text = "10000" };
            }

            if (_Gain == null)
            {
                _Gain = new LinkVarModel { Text = "0" };
            }

            if (_SpecifiedImagePathLink == null)
            {
                _SpecifiedImagePathLink = new LinkVarModel();
            }

            _currentCheckedIndex = 0;
            _batchCycleFinished = false;
            _isInternalSelectionUpdate = false;
            _executionGate = 0;
            _editorPreviewImage = null;
            HookItemPropertyChanged();
            UpdateBatchStatusText();
        }

        private void HookItemPropertyChanged()
        {
            if (ImageNameModels == null) return;
            foreach (var item in ImageNameModels)
            {
                item.PropertyChanged -= Item_PropertyChanged;
                item.PropertyChanged += Item_PropertyChanged;
            }
        }

        private void Item_PropertyChanged(object sender, PropertyChangedEventArgs e)
        {
            if (e.PropertyName == nameof(ImageNameModel.IsSelected))
            {
                _batchCycleFinished = false;
                UpdateBatchStatusText();
            }
        }

        public void UpdateBatchStatusText()
        {
            if (ImageNameModels == null || ImageNameModels.Count == 0)
            {
                BatchStatusText = "无图像";
                return;
            }
            int selectedCount = ImageNameModels.Count(x => x.IsSelected);
            int totalCount = ImageNameModels.Count;
            BatchStatusText = $"勾选: {selectedCount}/{totalCount}";
        }

        private void RenumberItems()
        {
            if (ImageNameModels == null) return;
            for (int i = 0; i < ImageNameModels.Count; i++)
            {
                ImageNameModels[i].ID = i + 1;
            }
        }
        [NonSerialized]
        private CommandBase _ImagePathCommand;
        public CommandBase ImagePathCommand
        {
            get
            {
                if (_ImagePathCommand == null)
                {
                    _ImagePathCommand = new CommandBase((obj) =>
                    {
                        Microsoft.Win32.OpenFileDialog dlg = new Microsoft.Win32.OpenFileDialog();
                        dlg.Filter = "所有图像文件 | *.bmp; *.pcx; *.png; *.jpg; *.gif;*.tif; *.ico; *.dxf; *.cgm; *.cdr; *.wmf; *.eps; *.emf";
                        if (dlg.ShowDialog() == true)
                        {
                            ImagePath = dlg.FileName;
                            ExecuteForEditorPreview();
                        }

                    });
                }
                return _ImagePathCommand;
            }
        }
        [NonSerialized]
        private CommandBase _FilePathCommand;
        public CommandBase FilePathCommand
        {
            get
            {
                if (_FilePathCommand == null)
                {
                    _FilePathCommand = new CommandBase((obj) =>
                    {
                        CommonOpenFileDialog dialog = new CommonOpenFileDialog{IsFolderPicker = true};

                        if (dialog.ShowDialog() == CommonFileDialogResult.Ok)
                        {
                            FilePath = dialog.FileName;
                            var files = Directory.GetFiles(FilePath, "*.*", SearchOption.AllDirectories).Where(s => s.EndsWith(".jpg") || s.EndsWith(".gif") || s.EndsWith(".png") || s.EndsWith(".bmp") || s.EndsWith(".jpg") || s.EndsWith(".eps") || s.EndsWith(".tif"));
                            if (files.Any())
                            {
                                var names = files.ToList();
                                ImageNameModels.Clear();
                                for (int i = 0; i < names.Count; i++)
                                {
                                    ImageNameModels.Add(new ImageNameModel() { ID = i + 1,ImagePath=names[i], ImageName = Path.GetFileName(names[i]), IsSelected = true });
                                }
                                HookItemPropertyChanged();
                                _currentCheckedIndex = 0;
                                _batchCycleFinished = false;
                                UpdateBatchStatusText();
                                RImage nextPreviewImage = null;
                                if (ImageNameModels!=null && ImageNameModels.Count>0 && File.Exists(ImageNameModels[0].ImagePath))
                                {
                                    SelectedIndex = 0;
                                    nextPreviewImage = LoadImageToDisplayBuffer(ImageNameModels[0].ImagePath);
                                }
                                ReplaceEditorPreviewImage(nextPreviewImage);
                                ShowEditorPreview(_editorPreviewImage);

                            }
                        }

                    });
                }
                return _FilePathCommand;
            }
        }

        [NonSerialized]
        private CommandBase _SpecifiedImage_LinkPathCommand;
        public CommandBase SpecifiedImage_LinkPathCommand
        {
            get
            {
                if (_SpecifiedImage_LinkPathCommand == null)
                {
                    _SpecifiedImage_LinkPathCommand = new CommandBase((obj) =>
                    {
                    });
                }
                return _SpecifiedImage_LinkPathCommand;
            }
        }
        [NonSerialized]
        private CommandBase _ExecuteCommand;
        public CommandBase ExecuteCommand
        {
            get
            {
                if (_ExecuteCommand == null)
                {
                    _ExecuteCommand = new CommandBase((obj) =>
                    {
                        ExecuteForEditorPreview();
                    });
                }
                return _ExecuteCommand;
            }
        }
        [NonSerialized]
        private CommandBase _ConfirmCommand;
        public CommandBase ConfirmCommand
        {
            get
            {
                if (_ConfirmCommand == null)
                {
                    _ConfirmCommand = new CommandBase((obj) =>
                    {
                        var view = this.ModuleView as GrabImageView;
                        if (view != null)
                        {
                            view.Close();
                        }
                    });
                }
                return _ConfirmCommand;
            }
        }
        [NonSerialized]
        private CommandBase _PreviewMouseDoubleClick_FilePath;
        public CommandBase PreviewMouseDoubleClick_FilePath
        {
            get
            {
                if (_PreviewMouseDoubleClick_FilePath == null)
                {
                    _PreviewMouseDoubleClick_FilePath = new CommandBase((obj) =>
                    {
                        if (Volatile.Read(ref _executionGate) != 0)
                        {
                            return;
                        }

                        if (ImageNameModels == null
                            || SelectedIndex < 0
                            || SelectedIndex >= ImageNameModels.Count
                            || ImageNameModels[SelectedIndex] == null)
                        {
                            return;
                        }

                        ReplaceEditorPreviewImage(
                            LoadImageToDisplayBuffer(ImageNameModels[SelectedIndex].ImagePath));
                        ShowEditorPreview(_editorPreviewImage);
                    });
                }
                return _PreviewMouseDoubleClick_FilePath;
            }
        }
        [NonSerialized]
        private CommandBase _LinkCommand;
        public CommandBase LinkCommand
        {
            get
            {
                if (_LinkCommand == null)
                {
                    //以GUID+类名作为筛选器
                    if (_varChangedToken == null)
                    {
                        _varChangedToken = EventMgr.Ins.GetEvent<VarChangedEvent>()
                            .Subscribe(OnVarChanged, o => !string.IsNullOrEmpty(o.SendName)
                                && o.SendName.StartsWith($"{ModuleGuid}"));
                    }
                    _LinkCommand = new CommandBase((obj) =>
                    {
                        eLinkCommand linkCommand = (eLinkCommand)obj;
                        switch (linkCommand)
                        {
                            case eLinkCommand.ExposureTime:
                                CommonMethods.GetModuleList(ModuleParam, VarLinkViewModel.Ins.Modules, VariableTypes.Int);
                                EventMgr.Ins.GetEvent<OpenVarLinkViewEvent>().Publish($"{ModuleGuid},ExposureTimeLink");
                                break;
                            case eLinkCommand.Gain:
                                CommonMethods.GetModuleList(ModuleParam, VarLinkViewModel.Ins.Modules, VariableTypes.Int);
                                EventMgr.Ins.GetEvent<OpenVarLinkViewEvent>().Publish($"{ModuleGuid},GainLink");
                                break;
                            case eLinkCommand.SpecifiedImagePath:
                                CommonMethods.GetModuleList(ModuleParam, VarLinkViewModel.Ins.Modules, VariableTypes.String);
                                EventMgr.Ins.GetEvent<OpenVarLinkViewEvent>().Publish($"{ModuleGuid},SpecifiedImagePathLink");
                                break;
                            default:
                                break;
                        }

                    });
                }
                return _LinkCommand;
            }
        }
        private void OnVarChanged(VarChangedEventParamModel obj)
        {
            if (obj == null || string.IsNullOrEmpty(obj.SendName))
            {
                return;
            }

            string[] parts = obj.SendName.Split(',');
            if (parts.Length < 2)
            {
                return;
            }

            switch (parts[1])
            {
                case "ExposureTimeLink":
                    ExposureTime.Text= obj.LinkName;
                    break;
                case "GainLink":
                    Gain.Text = obj.LinkName;
                    break;
                case "SpecifiedImagePathLink":
                    SpecifiedImagePathLink.Text = obj.LinkName;
                    break;
                default:
                    break;
            }
        }

        #region Batch Run Commands
        [NonSerialized]
        private CommandBase _SelectAllCommand;
        public CommandBase SelectAllCommand
        {
            get
            {
                if (_SelectAllCommand == null)
                {
                    _SelectAllCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null) return;
                        foreach (var item in ImageNameModels)
                        {
                            item.IsSelected = true;
                        }
                        _batchCycleFinished = false;
                        UpdateBatchStatusText();
                    });
                }
                return _SelectAllCommand;
            }
        }

        [NonSerialized]
        private CommandBase _UnselectAllCommand;
        public CommandBase UnselectAllCommand
        {
            get
            {
                if (_UnselectAllCommand == null)
                {
                    _UnselectAllCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null) return;
                        foreach (var item in ImageNameModels)
                        {
                            item.IsSelected = false;
                        }
                        _batchCycleFinished = false;
                        UpdateBatchStatusText();
                    });
                }
                return _UnselectAllCommand;
            }
        }

        [NonSerialized]
        private CommandBase _InvertSelectCommand;
        public CommandBase InvertSelectCommand
        {
            get
            {
                if (_InvertSelectCommand == null)
                {
                    _InvertSelectCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null) return;
                        foreach (var item in ImageNameModels)
                        {
                            item.IsSelected = !item.IsSelected;
                        }
                        _batchCycleFinished = false;
                        UpdateBatchStatusText();
                    });
                }
                return _InvertSelectCommand;
            }
        }

        [NonSerialized]
        private CommandBase _MoveUpCommand;
        public CommandBase MoveUpCommand
        {
            get
            {
                if (_MoveUpCommand == null)
                {
                    _MoveUpCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null || SelectedIndex <= 0 || SelectedIndex >= ImageNameModels.Count) return;
                        int idx = SelectedIndex;
                        var item = ImageNameModels[idx];
                        _isInternalSelectionUpdate = true;
                        try
                        {
                            ImageNameModels.RemoveAt(idx);
                            ImageNameModels.Insert(idx - 1, item);
                            RenumberItems();
                            SelectedIndex = idx - 1;
                        }
                        finally
                        {
                            _isInternalSelectionUpdate = false;
                        }
                        ScrollToCurrentItem(SelectedIndex);
                    });
                }
                return _MoveUpCommand;
            }
        }

        [NonSerialized]
        private CommandBase _MoveDownCommand;
        public CommandBase MoveDownCommand
        {
            get
            {
                if (_MoveDownCommand == null)
                {
                    _MoveDownCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null || SelectedIndex < 0 || SelectedIndex >= ImageNameModels.Count - 1) return;
                        int idx = SelectedIndex;
                        var item = ImageNameModels[idx];
                        _isInternalSelectionUpdate = true;
                        try
                        {
                            ImageNameModels.RemoveAt(idx);
                            ImageNameModels.Insert(idx + 1, item);
                            RenumberItems();
                            SelectedIndex = idx + 1;
                        }
                        finally
                        {
                            _isInternalSelectionUpdate = false;
                        }
                        ScrollToCurrentItem(SelectedIndex);
                    });
                }
                return _MoveDownCommand;
            }
        }

        [NonSerialized]
        private CommandBase _SortByNameCommand;
        public CommandBase SortByNameCommand
        {
            get
            {
                if (_SortByNameCommand == null)
                {
                    _SortByNameCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null || ImageNameModels.Count == 0) return;
                        var sorted = ImageNameModels.OrderBy(x => x.ImageName).ToList();
                        _isInternalSelectionUpdate = true;
                        try
                        {
                            ImageNameModels.Clear();
                            for (int i = 0; i < sorted.Count; i++)
                            {
                                sorted[i].ID = i + 1;
                                ImageNameModels.Add(sorted[i]);
                            }
                            SelectedIndex = 0;
                        }
                        finally
                        {
                            _isInternalSelectionUpdate = false;
                        }
                        UpdateBatchStatusText();
                    });
                }
                return _SortByNameCommand;
            }
        }

        [NonSerialized]
        private CommandBase _SortByTimeCommand;
        public CommandBase SortByTimeCommand
        {
            get
            {
                if (_SortByTimeCommand == null)
                {
                    _SortByTimeCommand = new CommandBase((obj) =>
                    {
                        if (ImageNameModels == null || ImageNameModels.Count == 0) return;
                        var sorted = ImageNameModels.OrderBy(x =>
                        {
                            try { return File.GetLastWriteTime(x.ImagePath); }
                            catch { return DateTime.MinValue; }
                        }).ToList();
                        _isInternalSelectionUpdate = true;
                        try
                        {
                            ImageNameModels.Clear();
                            for (int i = 0; i < sorted.Count; i++)
                            {
                                sorted[i].ID = i + 1;
                                ImageNameModels.Add(sorted[i]);
                            }
                            SelectedIndex = 0;
                        }
                        finally
                        {
                            _isInternalSelectionUpdate = false;
                        }
                        UpdateBatchStatusText();
                    });
                }
                return _SortByTimeCommand;
            }
        }
        #endregion

        #endregion

    }
}
```

---

### 文件 6: `Views/GrabImageView.xaml.cs`

- **相对路径**: `Views/GrabImageView.xaml.cs`
- **文件类型**: `C# 源码`
- **文件大小**: `3.16 KB`
- **命名空间**: `Plugin.GrabImage.Views`
- **核心类型**: `class GrabImageView`
- **依赖摘要**: `无明显构造注入依赖`
- **概要**: 核心 C# 类型定义或业务代码

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

```csharp
﻿using HalconDotNet;
using Plugin.GrabImage.ViewModels;
using System;
using System.IO;
using System.Windows;
using VM.Halcon;
using VM.Halcon.Config;
using VM.Start.Common.Enums;
using VM.Start.Common.Provide;
using VM.Start.Communacation;
using VM.Start.Core;
using VM.Start.Views.Dock;

namespace Plugin.GrabImage.Views
{
    /// <summary>
    /// GrabImageModuleView.xaml 的交互逻辑
    /// </summary>
    public partial class GrabImageView : ModuleViewBase
    {
        public GrabImageView()
        {
            // 有用户反馈二次启动后打开界面会报 URI 资源找不到，此处增加容错：
            // 先用默认相对 URI 的 InitializeComponent，失败则改用绝对 pack URI 再尝试一次。
            try
            {
                InitializeComponent();
            }
            catch (Exception ee)
            {
                var uri = new Uri("pack://application:,,,/Plugin.GrabImage;component/Views/GrabImageView.xaml", UriKind.Absolute);
                System.Windows.Application.LoadComponent(this, uri);
            }

            EnsureWindowControl();
        }

        private void EnsureWindowControl()
        {
            if (mWindowH == null)
            {
                mWindowH = new VMHWindowControl();
                winFormHost.Child = mWindowH;
            }
        }

        public void DisplayImage(RImage image)
        {
            if (image == null || !image.IsInitialized())
            {
                return;
            }

            EnsureWindowControl();

            try
            {
                mWindowH.SetBackgroundImage(new HImage(image), true, true);
                mWindowH.DispImageFitImage();
            }
            catch (Exception ex)
            {
                Logger.GetExceptionMsg(ex);
            }
        }

        public void DisplayImage(HObject image)
        {
            if (image == null || !image.IsInitialized())
            {
                return;
            }

            DisplayImage(new RImage(image));
        }

        public void ClearDisplay()
        {
            if (mWindowH == null)
            {
                return;
            }

            try
            {
                mWindowH.ClearDisplayLayers(true, true, true);
            }
            catch (Exception ex)
            {
                Logger.GetExceptionMsg(ex);
            }
        }

        GrabImageViewModel viewModel;

        private void btnCancel_Click(object sender, RoutedEventArgs e)
        {
            this.Close();
        }

        #region Method
        private void InitData()
        {
            //var viewModel1 = DataContext as GrabImageViewModel;
            //if (viewModel1 == null) return;

            //viewModel1.AcquisitionModes = ;//EComManageer.GetPLCConnectKeys();
            ////viewModel1.upDataRemaks();
        }
        #endregion

        private void ModuleViewBase_Activated(object sender, System.EventArgs e)
        {

        }

        private void ModuleViewBase_Loaded(object sender, RoutedEventArgs e)
        {

        }
    }
}
```

---

### 文件 7: `Properties/DesignTimeResources.xaml`

- **相对路径**: `Properties/DesignTimeResources.xaml`
- **文件类型**: `WPF/XAML 文件`
- **文件大小**: `1005 B`
- **概要**: WPF/XAML 界面布局或资源定义文件

```xml
﻿<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                    xmlns:mah="http://metro.mahapps.com/winfx/xaml/controls">
    <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="pack://application:,,,/HandyControl;component/Themes/SkinDark.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/HandyControl;component/Themes/Theme.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Controls.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Fonts.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/MahApps.Metro;component/Styles/Themes/Dark.Purple.xaml"/>
        <ResourceDictionary Source="pack://application:,,,/VM.Start;component/Assets/Collection.xaml" />
    </ResourceDictionary.MergedDictionaries>
</ResourceDictionary>
```

---

### 文件 8: `app.config`

© 苏州机器视觉 老T ·  Mr.T Vision 机器视觉平台：开放·包容·进取， 欢迎关注微信视频号“苏州机器视觉”

- **相对路径**: `app.config`
- **文件类型**: `XML 配置文件`
- **文件大小**: `666 B`
- **概要**: XML 配置文件

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <dependentAssembly>
        <assemblyIdentity name="ControlzEx" publicKeyToken="69f1c32f803d307e" culture="neutral" />
        <bindingRedirect oldVersion="0.0.0.0-5.0.0.0" newVersion="5.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="Newtonsoft.Json" publicKeyToken="30ad4fe6b2a6aeed" culture="neutral" />
        <bindingRedirect oldVersion="0.0.0.0-13.0.0.0" newVersion="13.0.0.0" />
      </dependentAssembly>
    </assemblyBinding>
  </runtime>
</configuration>
```

---

### 文件 9: `packages.config`

- **相对路径**: `packages.config`
- **文件类型**: `XML 配置文件`
- **文件大小**: `498 B`
- **概要**: XML 配置文件

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<packages>
  <package id="ControlzEx" version="5.0.2" targetFramework="net472" />
  <package id="HandyControl" version="3.4.0" targetFramework="net472" />
  <package id="Microsoft.WindowsAPICodePack-Core" version="1.1.0.0" targetFramework="net472" />
  <package id="Microsoft.WindowsAPICodePack-Shell" version="1.1.0.0" targetFramework="net472" />
  <package id="Microsoft.Xaml.Behaviors.Wpf" version="1.1.31" targetFramework="net472" />
</packages>
```

---

