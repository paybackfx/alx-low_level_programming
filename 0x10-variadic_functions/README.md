<!-- A variadic function is a function in programming that can accept an indefinite number of arguments. In other words, the function can be called with a variable number of arguments.

In C programming, a variadic function is created using the ellipsis (…) syntax in the function declaration. The ellipsis is used to indicate that the function takes a variable number of arguments. The va_list and va_arg macros are used to access the arguments passed to the function. -->
<!-- exemple: -->

#include <stdarg.h>

int sum(int count, ...) {
    int result = 0;

    va_list args;
    va_start(args, count);

    for (int i = 0; i < count; i++) {
        result += va_arg(args, int);
    }

    va_end(args);

    return result;
}

<!-- In this example, the first argument of the function is the number of integers to sum, followed by the integers themselves. The va_start macro initializes the va_list argument pointer, and the va_arg macro retrieves each integer argument. The va_end macro is called to clean up the argument list after the function is finished.

Variadic functions are useful for cases where the number of arguments passed to a function may vary, such as in printf() or scanf() functions, or when implementing a function that needs to be flexible in the number of arguments it takes. -->