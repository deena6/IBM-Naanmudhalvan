{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "NSsrvs8V1c70",
        "outputId": "8e055891-fde8-49ed-e6d9-eb8288cb5c35"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "               DateTime         Holiday  HolidayFlag  DayOfWeek  WeekOfYear  \\\n",
            "0      01/11/2011 00:00            None            0          1          44   \n",
            "1      01/11/2011 00:30            None            0          1          44   \n",
            "2      01/11/2011 01:00            None            0          1          44   \n",
            "3      01/11/2011 01:30            None            0          1          44   \n",
            "4      01/11/2011 02:00            None            0          1          44   \n",
            "...                 ...             ...          ...        ...         ...   \n",
            "38009  31/12/2013 21:30  New Year's Eve            1          1           1   \n",
            "38010  31/12/2013 22:00  New Year's Eve            1          1           1   \n",
            "38011  31/12/2013 22:30  New Year's Eve            1          1           1   \n",
            "38012  31/12/2013 23:00  New Year's Eve            1          1           1   \n",
            "38013  31/12/2013 23:30  New Year's Eve            1          1           1   \n",
            "\n",
            "       Day  Month  Year  PeriodOfDay ForecastWindProduction SystemLoadEA  \\\n",
            "0        1     11  2011            0                 315.31      3388.77   \n",
            "1        1     11  2011            1                 321.80      3196.66   \n",
            "2        1     11  2011            2                 328.57      3060.71   \n",
            "3        1     11  2011            3                 335.60      2945.56   \n",
            "4        1     11  2011            4                 342.90      2849.34   \n",
            "...    ...    ...   ...          ...                    ...          ...   \n",
            "38009   31     12  2013           43                1179.14      3932.22   \n",
            "38010   31     12  2013           44                1152.01      3821.44   \n",
            "38011   31     12  2013           45                1123.67      3724.21   \n",
            "38012   31     12  2013           46                1094.24      3638.16   \n",
            "38013   31     12  2013           47                 1064.0      3624.25   \n",
            "\n",
            "       SMPEA ORKTemperature ORKWindspeed CO2Intensity ActualWindProduction  \\\n",
            "0      49.26           6.00         9.30       600.71               356.00   \n",
            "1      49.26           6.00        11.10       605.42               317.00   \n",
            "2      49.10           5.00        11.10       589.97               311.00   \n",
            "3      48.04           6.00         9.30       585.94               313.00   \n",
            "4      33.75           6.00        11.10       571.52               346.00   \n",
            "...      ...            ...          ...          ...                  ...   \n",
            "38009  34.51           6.00        22.20       285.31                812.0   \n",
            "38010  33.83           5.00        24.10       278.31                852.0   \n",
            "38011  31.75           4.00        20.40       280.91                962.0   \n",
            "38012  33.83           5.00        14.80       302.46                950.0   \n",
            "38013  33.83           5.00        16.70       308.01               1020.0   \n",
            "\n",
            "      SystemLoadEP2 SMPEP2  \n",
            "0           3159.60  54.32  \n",
            "1           2973.01  54.23  \n",
            "2           2834.00  54.23  \n",
            "3           2725.99  53.47  \n",
            "4           2655.64  39.87  \n",
            "...             ...    ...  \n",
            "38009       3692.95  42.45  \n",
            "38010        3571.0  33.83  \n",
            "38011       3460.29  31.75  \n",
            "38012       3563.99   50.6  \n",
            "38013       3517.08   34.9  \n",
            "\n",
            "[38014 rows x 18 columns]\n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-1-0b157523f781>:3: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ],
      "source": [
        "#Uploading and Displaying Dataset\n",
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "print(df)"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "# creating a list of column names\n",
        "Column_name = pd.DataFrame(df.columns)\n",
        "print('List of column names :',Column_name)\n"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "8Eav6DqL192n",
        "outputId": "a208d953-13d5-4846-d645-7ddaf33ab666"
      },
      "execution_count": 2,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "List of column names :                          0\n",
            "0                 DateTime\n",
            "1                  Holiday\n",
            "2              HolidayFlag\n",
            "3                DayOfWeek\n",
            "4               WeekOfYear\n",
            "5                      Day\n",
            "6                    Month\n",
            "7                     Year\n",
            "8              PeriodOfDay\n",
            "9   ForecastWindProduction\n",
            "10            SystemLoadEA\n",
            "11                   SMPEA\n",
            "12          ORKTemperature\n",
            "13            ORKWindspeed\n",
            "14            CO2Intensity\n",
            "15    ActualWindProduction\n",
            "16           SystemLoadEP2\n",
            "17                  SMPEP2\n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-2-26dc719d487c>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Displaying First 5 rows\n",
        "print(df.head())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "4K3kLB6K2dpE",
        "outputId": "90545cc2-2c79-4d1d-afc8-88052308d0f6"
      },
      "execution_count": 3,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "           DateTime Holiday  HolidayFlag  DayOfWeek  WeekOfYear  Day  Month  \\\n",
            "0  01/11/2011 00:00    None            0          1          44    1     11   \n",
            "1  01/11/2011 00:30    None            0          1          44    1     11   \n",
            "2  01/11/2011 01:00    None            0          1          44    1     11   \n",
            "3  01/11/2011 01:30    None            0          1          44    1     11   \n",
            "4  01/11/2011 02:00    None            0          1          44    1     11   \n",
            "\n",
            "   Year  PeriodOfDay ForecastWindProduction SystemLoadEA  SMPEA  \\\n",
            "0  2011            0                 315.31      3388.77  49.26   \n",
            "1  2011            1                 321.80      3196.66  49.26   \n",
            "2  2011            2                 328.57      3060.71  49.10   \n",
            "3  2011            3                 335.60      2945.56  48.04   \n",
            "4  2011            4                 342.90      2849.34  33.75   \n",
            "\n",
            "  ORKTemperature ORKWindspeed CO2Intensity ActualWindProduction SystemLoadEP2  \\\n",
            "0           6.00         9.30       600.71               356.00       3159.60   \n",
            "1           6.00        11.10       605.42               317.00       2973.01   \n",
            "2           5.00        11.10       589.97               311.00       2834.00   \n",
            "3           6.00         9.30       585.94               313.00       2725.99   \n",
            "4           6.00        11.10       571.52               346.00       2655.64   \n",
            "\n",
            "  SMPEP2  \n",
            "0  54.32  \n",
            "1  54.23  \n",
            "2  54.23  \n",
            "3  53.47  \n",
            "4  39.87  \n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-3-77ea95c273fa>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Displaying Last 5 rows\n",
        "print(df.tail())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "TcMGfbgw3Ebn",
        "outputId": "9d4614b2-2af6-4e47-d075-fd1cfdf6d982"
      },
      "execution_count": 4,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "               DateTime         Holiday  HolidayFlag  DayOfWeek  WeekOfYear  \\\n",
            "38009  31/12/2013 21:30  New Year's Eve            1          1           1   \n",
            "38010  31/12/2013 22:00  New Year's Eve            1          1           1   \n",
            "38011  31/12/2013 22:30  New Year's Eve            1          1           1   \n",
            "38012  31/12/2013 23:00  New Year's Eve            1          1           1   \n",
            "38013  31/12/2013 23:30  New Year's Eve            1          1           1   \n",
            "\n",
            "       Day  Month  Year  PeriodOfDay ForecastWindProduction SystemLoadEA  \\\n",
            "38009   31     12  2013           43                1179.14      3932.22   \n",
            "38010   31     12  2013           44                1152.01      3821.44   \n",
            "38011   31     12  2013           45                1123.67      3724.21   \n",
            "38012   31     12  2013           46                1094.24      3638.16   \n",
            "38013   31     12  2013           47                 1064.0      3624.25   \n",
            "\n",
            "       SMPEA ORKTemperature ORKWindspeed CO2Intensity ActualWindProduction  \\\n",
            "38009  34.51           6.00        22.20       285.31                812.0   \n",
            "38010  33.83           5.00        24.10       278.31                852.0   \n",
            "38011  31.75           4.00        20.40       280.91                962.0   \n",
            "38012  33.83           5.00        14.80       302.46                950.0   \n",
            "38013  33.83           5.00        16.70       308.01               1020.0   \n",
            "\n",
            "      SystemLoadEP2 SMPEP2  \n",
            "38009       3692.95  42.45  \n",
            "38010        3571.0  33.83  \n",
            "38011       3460.29  31.75  \n",
            "38012       3563.99   50.6  \n",
            "38013       3517.08   34.9  \n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-4-f4c0c49e4f43>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Data Manipulation\n",
        "print(\"shape of dataframe\", df.shape)\n",
        "print(\"number of rows : \", df.shape[0])\n",
        "print(\"number of columns : \", df.shape[1])\n",
        "print(\"DataFrame Size : \", df.size)\n",
        "print('Info: ', df.info())\n",
        "print('Correlation: ', df.corr())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "iM5ImW7V3cJL",
        "outputId": "aaea387e-44b7-47b0-ad8e-e7c71d3b2b37"
      },
      "execution_count": 5,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "shape of dataframe (38014, 18)\n",
            "number of rows :  38014\n",
            "number of columns :  18\n",
            "DataFrame Size :  684252\n",
            "<class 'pandas.core.frame.DataFrame'>\n",
            "RangeIndex: 38014 entries, 0 to 38013\n",
            "Data columns (total 18 columns):\n",
            " #   Column                  Non-Null Count  Dtype \n",
            "---  ------                  --------------  ----- \n",
            " 0   DateTime                38014 non-null  object\n",
            " 1   Holiday                 38014 non-null  object\n",
            " 2   HolidayFlag             38014 non-null  int64 \n",
            " 3   DayOfWeek               38014 non-null  int64 \n",
            " 4   WeekOfYear              38014 non-null  int64 \n",
            " 5   Day                     38014 non-null  int64 \n",
            " 6   Month                   38014 non-null  int64 \n",
            " 7   Year                    38014 non-null  int64 \n",
            " 8   PeriodOfDay             38014 non-null  int64 \n",
            " 9   ForecastWindProduction  38014 non-null  object\n",
            " 10  SystemLoadEA            38014 non-null  object\n",
            " 11  SMPEA                   38014 non-null  object\n",
            " 12  ORKTemperature          38014 non-null  object\n",
            " 13  ORKWindspeed            38014 non-null  object\n",
            " 14  CO2Intensity            38014 non-null  object\n",
            " 15  ActualWindProduction    38014 non-null  object\n",
            " 16  SystemLoadEP2           38014 non-null  object\n",
            " 17  SMPEP2                  38014 non-null  object\n",
            "dtypes: int64(7), object(11)\n",
            "memory usage: 5.2+ MB\n",
            "Info:  None\n",
            "Correlation:               HolidayFlag  DayOfWeek  WeekOfYear       Day     Month      Year  \\\n",
            "HolidayFlag     1.000000  -0.124773   -0.003286  0.046133  0.032414 -0.023431   \n",
            "DayOfWeek      -0.124773   1.000000    0.007504 -0.004423  0.003056 -0.001196   \n",
            "WeekOfYear     -0.003286   0.007504    1.000000  0.060816  0.971182 -0.237323   \n",
            "Day             0.046133  -0.004423    0.060816  1.000000  0.008698 -0.001786   \n",
            "Month           0.032414   0.003056    0.971182  0.008698  1.000000 -0.236833   \n",
            "Year           -0.023431  -0.001196   -0.237323 -0.001786 -0.236833  1.000000   \n",
            "PeriodOfDay    -0.000016   0.000120   -0.000083  0.000084 -0.000087 -0.000049   \n",
            "\n",
            "             PeriodOfDay  \n",
            "HolidayFlag    -0.000016  \n",
            "DayOfWeek       0.000120  \n",
            "WeekOfYear     -0.000083  \n",
            "Day             0.000084  \n",
            "Month          -0.000087  \n",
            "Year           -0.000049  \n",
            "PeriodOfDay     1.000000  \n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-5-3ece6edf4382>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n",
            "<ipython-input-5-3ece6edf4382>:10: FutureWarning: The default value of numeric_only in DataFrame.corr is deprecated. In a future version, it will default to False. Select only valid columns or specify the value of numeric_only to silence this warning.\n",
            "  print('Correlation: ', df.corr())\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Dropping Empty Cells\n",
        "Emp_drop = df.dropna(how= \"all\", axis=1)\n",
        "print(df)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "Ce2HyHWY6ixR",
        "outputId": "f851877d-b067-4bad-ffa0-872219864350"
      },
      "execution_count": 6,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "               DateTime         Holiday  HolidayFlag  DayOfWeek  WeekOfYear  \\\n",
            "0      01/11/2011 00:00            None            0          1          44   \n",
            "1      01/11/2011 00:30            None            0          1          44   \n",
            "2      01/11/2011 01:00            None            0          1          44   \n",
            "3      01/11/2011 01:30            None            0          1          44   \n",
            "4      01/11/2011 02:00            None            0          1          44   \n",
            "...                 ...             ...          ...        ...         ...   \n",
            "38009  31/12/2013 21:30  New Year's Eve            1          1           1   \n",
            "38010  31/12/2013 22:00  New Year's Eve            1          1           1   \n",
            "38011  31/12/2013 22:30  New Year's Eve            1          1           1   \n",
            "38012  31/12/2013 23:00  New Year's Eve            1          1           1   \n",
            "38013  31/12/2013 23:30  New Year's Eve            1          1           1   \n",
            "\n",
            "       Day  Month  Year  PeriodOfDay ForecastWindProduction SystemLoadEA  \\\n",
            "0        1     11  2011            0                 315.31      3388.77   \n",
            "1        1     11  2011            1                 321.80      3196.66   \n",
            "2        1     11  2011            2                 328.57      3060.71   \n",
            "3        1     11  2011            3                 335.60      2945.56   \n",
            "4        1     11  2011            4                 342.90      2849.34   \n",
            "...    ...    ...   ...          ...                    ...          ...   \n",
            "38009   31     12  2013           43                1179.14      3932.22   \n",
            "38010   31     12  2013           44                1152.01      3821.44   \n",
            "38011   31     12  2013           45                1123.67      3724.21   \n",
            "38012   31     12  2013           46                1094.24      3638.16   \n",
            "38013   31     12  2013           47                 1064.0      3624.25   \n",
            "\n",
            "       SMPEA ORKTemperature ORKWindspeed CO2Intensity ActualWindProduction  \\\n",
            "0      49.26           6.00         9.30       600.71               356.00   \n",
            "1      49.26           6.00        11.10       605.42               317.00   \n",
            "2      49.10           5.00        11.10       589.97               311.00   \n",
            "3      48.04           6.00         9.30       585.94               313.00   \n",
            "4      33.75           6.00        11.10       571.52               346.00   \n",
            "...      ...            ...          ...          ...                  ...   \n",
            "38009  34.51           6.00        22.20       285.31                812.0   \n",
            "38010  33.83           5.00        24.10       278.31                852.0   \n",
            "38011  31.75           4.00        20.40       280.91                962.0   \n",
            "38012  33.83           5.00        14.80       302.46                950.0   \n",
            "38013  33.83           5.00        16.70       308.01               1020.0   \n",
            "\n",
            "      SystemLoadEP2 SMPEP2  \n",
            "0           3159.60  54.32  \n",
            "1           2973.01  54.23  \n",
            "2           2834.00  54.23  \n",
            "3           2725.99  53.47  \n",
            "4           2655.64  39.87  \n",
            "...             ...    ...  \n",
            "38009       3692.95  42.45  \n",
            "38010        3571.0  33.83  \n",
            "38011       3460.29  31.75  \n",
            "38012       3563.99   50.6  \n",
            "38013       3517.08   34.9  \n",
            "\n",
            "[38014 rows x 18 columns]\n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-6-746fc9c8ecfd>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Dropping Empty Cells\n",
        "df = df.drop(columns=df.columns[1:3], inplace=True)\n",
        "print(df)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "2uye_4kk6kKO",
        "outputId": "67376272-f9d8-44be-f783-72bc63fb9f7b"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "None\n"
          ]
        },
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-7-ae6219f44c9d>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "print('Correlation: ', df.corr())\n",
        "\n"
      ],
      "metadata": {
        "id": "HX6tGjXl7D60"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Create Duplicate Columns\n",
        "pd.get_dummies(df)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "RSFuvzz27emR",
        "outputId": "9aa85647-01fd-4928-fd6e-d5efc80db30f"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "<ipython-input-1-543768425546>:2: DtypeWarning: Columns (9,10,11,14,15,16,17) have mixed types. Specify dtype option on import or set low_memory=False.\n",
            "  df = pd.read_csv('/content/Electricity.csv')\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "#Take care of missing data(just for first 5 rows)\n",
        "df = df.head(5)\n",
        "df.notnull()"
      ],
      "metadata": {
        "id": "cMSmduZA9azi"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "df = pd.read_csv('/content/Electricity.csv')\n",
        "\n",
        "# Shuffle dataframe\n",
        "df = df.sample(frac=1)\n",
        "print(df)"
      ],
      "metadata": {
        "id": "7-zuEiuU94lr"
      },
      "execution_count": null,
      "outputs": []
    }
  ]
}
