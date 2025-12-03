## Code

    #include "mcc_generated_files/system/system.h"

    int main(void)
    {
      SYSTEM_Initialize();
      ADC_Initialize();
      UART1_Enable();
    
      adc_result_t analog_in = 0;

      while(1)
      {
    
        ADC_ChannelSelect(ADC_CHANNEL_ANA1);
        ADC_ConversionStart();
        while (!ADC_IsConversionDone());
        analog_in = (ADC_ConversionResultGet() - 1910) * 1.874; // -1910 to 2185 (without multiplier)
        printf("\n%d", analog_in);
        if (analog_in >= 2415) { // 2414.7 = 13 lbs
            IO_RD2_SetHigh();
        }
        else {
            IO_RD2_SetLow();
        }
      }
    }

## Zip File

[MPLAB X Files](SystemVerification.zip)
