# HPS Application Framework

Welcome to the HPS Application Framework documentation. This framework provides a robust foundation for building applications.

## Table of Contents

- [About](#about)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [API Reference](#api-reference)
- [Examples](#examples)

## About

The HPS Application Framework is a powerful tool for developing applications. It offers a wide range of features and capabilities to streamline your development process.

## Installation

To install the HPS Application Framework, follow these steps:

```

1. First, clone this repository to your local machine:
2. cd APP_Framework
3. Run qmake app.pro -r
4. make release -j 8

```

[Installation](Installation.md)

## Getting Started

To get started with the HPS Application Framework, check out the [Getting Started Guide](./docs/getting-started.md) for detailed instructions on how to create your first project.

## API Reference

For detailed information about the API provided by the HPS Application Framework, consult the [API Reference](API-Reference.md). This reference guide includes comprehensive documentation for all available classes, methods, and modules.


## Examples

To see practical examples of how to use the HPS Application Framework, refer to the [Examples](./examples) directory in this repository. You'll find a variety of sample projects that demonstrate different aspects of the framework.


---


```cpp

/*
///////////////////////////////////////////////////////////////////////////////////////////////////////////////
////  Model_Data_Structures   \                      | <--- User Intent <-------\                           ///
////  Model_Data_base ---------- <--> Controller <--/                           |-----> VIEW ( UI + Model ) ///
////  Model_Operation_Kernels /                     \ ---> Renderable Entity--->/                           ///
///////////////////////////////////////////////////////////////////////////////////////////////////////////////
*/

#include "app_core.hpp"

int main()
{
   HPS::controller app_controller; 
   
   app_controller.model_db.to_be_send_data = 100;
   app_controller.model_db.model.vertices.push_back(4.0);
   app_controller.model_db.model.vertices.push_back(4.0);
   app_controller.model_db.model.vertices.push_back(4.0);
  // HPS::Model m1 ;
  // app_controller.model_db.model_operation_kernels.model_scaling_operation(m1 , 6.0f);
   
   app_controller.pass_data_from_model_db_to_view();
   
   while(!app_controller.viewer.requested_exit())
   {   
     app_controller.present_view(); 
     app_controller.execute_intent();
   }
   
}



```
![sample code output (dark, segoeui font, freetype)](https://user-images.githubusercontent.com/8225057/191050833-b7ecf528-bfae-4a9f-ac1b-f3d83437a2f4.png)
![sample code output (light, segoeui font, freetype)](https://user-images.githubusercontent.com/8225057/191050838-8742efd4-504d-4334-a9a2-e756d15bc2ab.png)

```cpp


Feel free to explore the documentation and examples to make the most of the HPS Application Framework. If you encounter any issues or have questions, please don't hesitate to [open an issue](https://github.com/your-username/hps-application-framework/issues) on GitHub.

Happy coding!
