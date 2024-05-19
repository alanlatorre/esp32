#include <stdio.h>
#include "driver/gpio.h"
#include "freertos/freeRTOS.h"
#include "freertos/task.h"

#define pulsador 15

void app_main ()
{
	gpio_set_direction( 15, GPIO_MODE_INPUT );
	gpio_set_pull_mode(15, GPIO_PULLDOWN_ONLY);

	while (1)
	{
	bool level = gpio_get_level (15);
	printf ("nivel:  %d\n",level);
	vTaskDelay (100);
	}
}
