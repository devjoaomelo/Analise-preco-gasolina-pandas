# Analise-preco-gasolina-pandas
 
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "eb29fb7a-5c3a-46df-a5f9-627148c66351",
   "metadata": {},
   "source": [
    "## Exercícios"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ad2f7eba-5091-4fec-b113-487186883a09",
   "metadata": {},
   "source": [
    "Link para Dataset: https://www.kaggle.com/datasets/matheusfreitag/gas-prices-in-brazil"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "d0e9c6b9-3840-47a5-956f-9954b612c657",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "76366baf-6608-4ad2-b14b-ff048e5adb90",
   "metadata": {},
   "source": [
    "## Neste projeto, trabalharemos com dois arquivos csvs separados, contendo informações sobre o preço da gasolina no Brasil. \n",
    "\n",
    "### 1. Carregue os conjuntos de dados \"gasolina_2000+.csv\" e \"gasolina_2010+.csv\" em dois DataFrames diferentes e combine-os em um único DataFrame."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 38,
   "id": "c7decfae-2c39-48fb-8412-6dd2e789f28e",
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\joaom\\AppData\\Local\\Temp\\ipykernel_6312\\1776601843.py:2: DtypeWarning: Columns (12,14,15,16,17,18) have mixed types. Specify dtype option on import or set low_memory=False.\n",
      "  df2 = pd.read_csv(\"Data/gasolina_2010+.csv\",index_col=0)\n"
     ]
    }
   ],
   "source": [
    "df1 = pd.read_csv(\"Data/gasolina_2000+.csv\", index_col=0)\n",
    "df2 = pd.read_csv(\"Data/gasolina_2010+.csv\",index_col=0)\n",
    "\n",
    "df = pd.concat([df1, df2])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 44,
   "id": "45216c80",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>DATA INICIAL</th>\n",
       "      <th>DATA FINAL</th>\n",
       "      <th>REGIÃO</th>\n",
       "      <th>ESTADO</th>\n",
       "      <th>PRODUTO</th>\n",
       "      <th>NÚMERO DE POSTOS PESQUISADOS</th>\n",
       "      <th>UNIDADE DE MEDIDA</th>\n",
       "      <th>PREÇO MÉDIO REVENDA</th>\n",
       "      <th>DESVIO PADRÃO REVENDA</th>\n",
       "      <th>PREÇO MÍNIMO REVENDA</th>\n",
       "      <th>PREÇO MÁXIMO REVENDA</th>\n",
       "      <th>MARGEM MÉDIA REVENDA</th>\n",
       "      <th>COEF DE VARIAÇÃO REVENDA</th>\n",
       "      <th>PREÇO MÉDIO DISTRIBUIÇÃO</th>\n",
       "      <th>DESVIO PADRÃO DISTRIBUIÇÃO</th>\n",
       "      <th>PREÇO MÍNIMO DISTRIBUIÇÃO</th>\n",
       "      <th>PREÇO MÁXIMO DISTRIBUIÇÃO</th>\n",
       "      <th>COEF DE VARIAÇÃO DISTRIBUIÇÃO</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>CENTRO OESTE</td>\n",
       "      <td>DISTRITO FEDERAL</td>\n",
       "      <td>ETANOL HIDRATADO</td>\n",
       "      <td>127</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>1.288</td>\n",
       "      <td>0.016</td>\n",
       "      <td>1.19</td>\n",
       "      <td>1.350</td>\n",
       "      <td>0.463</td>\n",
       "      <td>0.012</td>\n",
       "      <td>0.825</td>\n",
       "      <td>0.11</td>\n",
       "      <td>0.4201</td>\n",
       "      <td>0.9666</td>\n",
       "      <td>0.133</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>CENTRO OESTE</td>\n",
       "      <td>GOIAS</td>\n",
       "      <td>ETANOL HIDRATADO</td>\n",
       "      <td>387</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>1.162</td>\n",
       "      <td>0.114</td>\n",
       "      <td>0.89</td>\n",
       "      <td>1.449</td>\n",
       "      <td>0.399</td>\n",
       "      <td>0.098</td>\n",
       "      <td>0.763</td>\n",
       "      <td>0.088</td>\n",
       "      <td>0.5013</td>\n",
       "      <td>1.05</td>\n",
       "      <td>0.115</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>CENTRO OESTE</td>\n",
       "      <td>MATO GROSSO</td>\n",
       "      <td>ETANOL HIDRATADO</td>\n",
       "      <td>192</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>1.389</td>\n",
       "      <td>0.097</td>\n",
       "      <td>1.18</td>\n",
       "      <td>1.760</td>\n",
       "      <td>0.419</td>\n",
       "      <td>0.070</td>\n",
       "      <td>0.97</td>\n",
       "      <td>0.095</td>\n",
       "      <td>0.5614</td>\n",
       "      <td>1.161</td>\n",
       "      <td>0.098</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>CENTRO OESTE</td>\n",
       "      <td>MATO GROSSO DO SUL</td>\n",
       "      <td>ETANOL HIDRATADO</td>\n",
       "      <td>162</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>1.262</td>\n",
       "      <td>0.070</td>\n",
       "      <td>1.09</td>\n",
       "      <td>1.509</td>\n",
       "      <td>0.432</td>\n",
       "      <td>0.055</td>\n",
       "      <td>0.83</td>\n",
       "      <td>0.119</td>\n",
       "      <td>0.5991</td>\n",
       "      <td>1.22242</td>\n",
       "      <td>0.143</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>NORDESTE</td>\n",
       "      <td>ALAGOAS</td>\n",
       "      <td>ETANOL HIDRATADO</td>\n",
       "      <td>103</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>1.181</td>\n",
       "      <td>0.078</td>\n",
       "      <td>1.05</td>\n",
       "      <td>1.400</td>\n",
       "      <td>0.24</td>\n",
       "      <td>0.066</td>\n",
       "      <td>0.941</td>\n",
       "      <td>0.077</td>\n",
       "      <td>0.7441</td>\n",
       "      <td>1.0317</td>\n",
       "      <td>0.082</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "  DATA INICIAL  DATA FINAL        REGIÃO              ESTADO  \\\n",
       "0   2004-05-09  2004-05-15  CENTRO OESTE    DISTRITO FEDERAL   \n",
       "1   2004-05-09  2004-05-15  CENTRO OESTE               GOIAS   \n",
       "2   2004-05-09  2004-05-15  CENTRO OESTE         MATO GROSSO   \n",
       "3   2004-05-09  2004-05-15  CENTRO OESTE  MATO GROSSO DO SUL   \n",
       "4   2004-05-09  2004-05-15      NORDESTE             ALAGOAS   \n",
       "\n",
       "            PRODUTO  NÚMERO DE POSTOS PESQUISADOS UNIDADE DE MEDIDA  \\\n",
       "0  ETANOL HIDRATADO                           127              R$/l   \n",
       "1  ETANOL HIDRATADO                           387              R$/l   \n",
       "2  ETANOL HIDRATADO                           192              R$/l   \n",
       "3  ETANOL HIDRATADO                           162              R$/l   \n",
       "4  ETANOL HIDRATADO                           103              R$/l   \n",
       "\n",
       "   PREÇO MÉDIO REVENDA  DESVIO PADRÃO REVENDA  PREÇO MÍNIMO REVENDA  \\\n",
       "0                1.288                  0.016                  1.19   \n",
       "1                1.162                  0.114                  0.89   \n",
       "2                1.389                  0.097                  1.18   \n",
       "3                1.262                  0.070                  1.09   \n",
       "4                1.181                  0.078                  1.05   \n",
       "\n",
       "   PREÇO MÁXIMO REVENDA MARGEM MÉDIA REVENDA  COEF DE VARIAÇÃO REVENDA  \\\n",
       "0                 1.350                0.463                     0.012   \n",
       "1                 1.449                0.399                     0.098   \n",
       "2                 1.760                0.419                     0.070   \n",
       "3                 1.509                0.432                     0.055   \n",
       "4                 1.400                 0.24                     0.066   \n",
       "\n",
       "  PREÇO MÉDIO DISTRIBUIÇÃO DESVIO PADRÃO DISTRIBUIÇÃO  \\\n",
       "0                    0.825                       0.11   \n",
       "1                    0.763                      0.088   \n",
       "2                     0.97                      0.095   \n",
       "3                     0.83                      0.119   \n",
       "4                    0.941                      0.077   \n",
       "\n",
       "  PREÇO MÍNIMO DISTRIBUIÇÃO PREÇO MÁXIMO DISTRIBUIÇÃO  \\\n",
       "0                    0.4201                    0.9666   \n",
       "1                    0.5013                      1.05   \n",
       "2                    0.5614                     1.161   \n",
       "3                    0.5991                   1.22242   \n",
       "4                    0.7441                    1.0317   \n",
       "\n",
       "  COEF DE VARIAÇÃO DISTRIBUIÇÃO  \n",
       "0                         0.133  \n",
       "1                         0.115  \n",
       "2                         0.098  \n",
       "3                         0.143  \n",
       "4                         0.082  "
      ]
     },
     "execution_count": 44,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "6cd74f39-565b-47ea-9171-9679eb964b1c",
   "metadata": {},
   "source": [
    "### 2.Investigue as colunas e entenda o conjunto de dados usando o head() e info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 43,
   "id": "079e63b5-4836-4332-86ee-11c804543571",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "Int64Index: 120823 entries, 0 to 120822\n",
      "Data columns (total 18 columns):\n",
      " #   Column                         Non-Null Count   Dtype  \n",
      "---  ------                         --------------   -----  \n",
      " 0   DATA INICIAL                   120823 non-null  object \n",
      " 1   DATA FINAL                     120823 non-null  object \n",
      " 2   REGIÃO                         120823 non-null  object \n",
      " 3   ESTADO                         120823 non-null  object \n",
      " 4   PRODUTO                        120823 non-null  object \n",
      " 5   NÚMERO DE POSTOS PESQUISADOS   120823 non-null  int64  \n",
      " 6   UNIDADE DE MEDIDA              120823 non-null  object \n",
      " 7   PREÇO MÉDIO REVENDA            120823 non-null  float64\n",
      " 8   DESVIO PADRÃO REVENDA          120823 non-null  float64\n",
      " 9   PREÇO MÍNIMO REVENDA           120823 non-null  float64\n",
      " 10  PREÇO MÁXIMO REVENDA           120823 non-null  float64\n",
      " 11  MARGEM MÉDIA REVENDA           120823 non-null  object \n",
      " 12  COEF DE VARIAÇÃO REVENDA       120823 non-null  float64\n",
      " 13  PREÇO MÉDIO DISTRIBUIÇÃO       120823 non-null  object \n",
      " 14  DESVIO PADRÃO DISTRIBUIÇÃO     120823 non-null  object \n",
      " 15  PREÇO MÍNIMO DISTRIBUIÇÃO      120823 non-null  object \n",
      " 16  PREÇO MÁXIMO DISTRIBUIÇÃO      120823 non-null  object \n",
      " 17  COEF DE VARIAÇÃO DISTRIBUIÇÃO  120823 non-null  object \n",
      "dtypes: float64(5), int64(1), object(12)\n",
      "memory usage: 21.5+ MB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "2bcb2d2f-1c32-4583-8981-ca5b6ed0e048",
   "metadata": {},
   "source": [
    "### 3. Selecione a terceira entrada da coluna DATA INICIAL e verifique seu tipo."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 49,
   "id": "c4399a8c-0ad3-4b6e-bcd8-d701438892fe",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'2004-05-09'"
      ]
     },
     "execution_count": 49,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df['DATA INICIAL'][2]"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7eda8c87-eef7-4b66-97ee-46629b214fc7",
   "metadata": {},
   "source": [
    "### 4. Você deve ter percebido que as colunas DATA INICIAL e DATA FINAL estão formatadas como string. Utilizando o método pd.to_datetime(), converta ambas colunas para Timestamp / Datetime."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 52,
   "id": "6813ae62-bdd0-4f73-8278-7fa0e0027f9c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0        2004-05-09\n",
       "1        2004-05-09\n",
       "2        2004-05-09\n",
       "3        2004-05-09\n",
       "4        2004-05-09\n",
       "            ...    \n",
       "120818   2021-04-25\n",
       "120819   2021-04-25\n",
       "120820   2021-04-25\n",
       "120821   2021-04-25\n",
       "120822   2021-04-25\n",
       "Name: DATA INICIAL, Length: 120823, dtype: datetime64[ns]"
      ]
     },
     "execution_count": 52,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df[\"DATA INICIAL\"] = pd.to_datetime(df[\"DATA INICIAL\"])\n",
    "df[\"DATA FINAL\"] = pd.to_datetime(df[\"DATA FINAL\"])\n",
    "df[\"DATA INICIAL\"]"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "2f9aaafa-f9a4-4f07-9bc6-86e5911c863c",
   "metadata": {},
   "source": [
    "### 5. Crie uma nova coluna para representar o ano e o mês(aaaa-mm), utilizando a coluna DATA FINAL como referência. "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 65,
   "id": "03f15a92-bae5-4256-add1-a7c97fe9f01d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0         2004-05\n",
       "1         2004-05\n",
       "2         2004-05\n",
       "3         2004-05\n",
       "4         2004-05\n",
       "           ...   \n",
       "120818    2021-05\n",
       "120819    2021-05\n",
       "120820    2021-05\n",
       "120821    2021-05\n",
       "120822    2021-05\n",
       "Name: ANO MES, Length: 120823, dtype: object"
      ]
     },
     "execution_count": 65,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df[\"ANO MES\"] = df['DATA FINAL'].apply(lambda x: str(x.year) + '-' + str(x.month).zfill(2))\n",
    "df[\"ANO MES\"]\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7d25e880-b153-4cce-8268-8388c3de52a3",
   "metadata": {},
   "source": [
    "### 6. Utilizando o value_counts(), liste todos os tipos de produtos contidos na base de dados."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 67,
   "id": "f953fa16-59bd-40d9-90c0-af138acb4191",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "GASOLINA COMUM        23570\n",
       "GLP                   23561\n",
       "ETANOL HIDRATADO      23440\n",
       "ÓLEO DIESEL           21194\n",
       "GNV                   14469\n",
       "ÓLEO DIESEL S10        9113\n",
       "OLEO DIESEL S10        2376\n",
       "OLEO DIESEL            2351\n",
       "GASOLINA ADITIVADA      749\n",
       "Name: PRODUTO, dtype: int64"
      ]
     },
     "execution_count": 67,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df['PRODUTO'].value_counts()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "fab0300f-7c49-48be-b95a-948601713229",
   "metadata": {},
   "source": [
    "### 7. Filtre o DataFrame para obter apenas dados da 'GASOLINA COMUM'. Grave em uma nova variável."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 75,
   "id": "6f1a53ad-2f8e-48b3-b1f3-05698caec5a7",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>DATA INICIAL</th>\n",
       "      <th>DATA FINAL</th>\n",
       "      <th>REGIÃO</th>\n",
       "      <th>ESTADO</th>\n",
       "      <th>PRODUTO</th>\n",
       "      <th>NÚMERO DE POSTOS PESQUISADOS</th>\n",
       "      <th>UNIDADE DE MEDIDA</th>\n",
       "      <th>PREÇO MÉDIO REVENDA</th>\n",
       "      <th>DESVIO PADRÃO REVENDA</th>\n",
       "      <th>PREÇO MÍNIMO REVENDA</th>\n",
       "      <th>PREÇO MÁXIMO REVENDA</th>\n",
       "      <th>MARGEM MÉDIA REVENDA</th>\n",
       "      <th>COEF DE VARIAÇÃO REVENDA</th>\n",
       "      <th>PREÇO MÉDIO DISTRIBUIÇÃO</th>\n",
       "      <th>DESVIO PADRÃO DISTRIBUIÇÃO</th>\n",
       "      <th>PREÇO MÍNIMO DISTRIBUIÇÃO</th>\n",
       "      <th>PREÇO MÁXIMO DISTRIBUIÇÃO</th>\n",
       "      <th>COEF DE VARIAÇÃO DISTRIBUIÇÃO</th>\n",
       "      <th>ANO MES</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>12064</th>\n",
       "      <td>2004-05-09</td>\n",
       "      <td>2004-05-15</td>\n",
       "      <td>CENTRO OESTE</td>\n",
       "      <td>DISTRITO FEDERAL</td>\n",
       "      <td>GASOLINA COMUM</td>\n",
       "      <td>128</td>\n",
       "      <td>R$/l</td>\n",
       "      <td>2.029</td>\n",
       "      <td>0.007</td>\n",
       "      <td>1.99</td>\n",
       "      <td>2.07</td>\n",
       "      <td>0.318</td>\n",
       "      <td>0.003</td>\n",
       "      <td>1.711</td>\n",
       "      <td>0.02</td>\n",
       "      <td>1.651</td>\n",
       "      <td>1.7427</td>\n",
       "      <td>0.012</td>\n",
       "      <td>2004-05</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "      DATA INICIAL DATA FINAL        REGIÃO            ESTADO         PRODUTO  \\\n",
       "12064   2004-05-09 2004-05-15  CENTRO OESTE  DISTRITO FEDERAL  GASOLINA COMUM   \n",
       "\n",
       "       NÚMERO DE POSTOS PESQUISADOS UNIDADE DE MEDIDA  PREÇO MÉDIO REVENDA  \\\n",
       "12064                           128              R$/l                2.029   \n",
       "\n",
       "       DESVIO PADRÃO REVENDA  PREÇO MÍNIMO REVENDA  PREÇO MÁXIMO REVENDA  \\\n",
       "12064                  0.007                  1.99                  2.07   \n",
       "\n",
       "      MARGEM MÉDIA REVENDA  COEF DE VARIAÇÃO REVENDA PREÇO MÉDIO DISTRIBUIÇÃO  \\\n",
       "12064                0.318                     0.003                    1.711   \n",
       "\n",
       "      DESVIO PADRÃO DISTRIBUIÇÃO PREÇO MÍNIMO DISTRIBUIÇÃO  \\\n",
       "12064                       0.02                     1.651   \n",
       "\n",
       "      PREÇO MÁXIMO DISTRIBUIÇÃO COEF DE VARIAÇÃO DISTRIBUIÇÃO  ANO MES  \n",
       "12064                    1.7427                         0.012  2004-05  "
      ]
     },
     "execution_count": 75,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df2 = df[df['PRODUTO'] == 'GASOLINA COMUM']\n",
    "df2.head(1)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "fb031b0b-51e7-43d7-b2cb-10da05019a73",
   "metadata": {},
   "source": [
    "### 8. Qual o preço médio de revenda da gasolina em agosto de 2008?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 81,
   "id": "3ba34e10-cc51-4b04-b67a-4245248907ed",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "2.6012444444444442"
      ]
     },
     "execution_count": 81,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df2[df2['ANO MES'] == '2008-08']['PREÇO MÉDIO REVENDA'].mean()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "a57428cc-e9e6-48f8-a7f7-27fb9c87bcde",
   "metadata": {},
   "source": [
    "### 9. Qual o preço médio de revenda da gasolina em maio de 2014 em São Paulo?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 84,
   "id": "e981678b-85db-499a-8466-e24c455ea20c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "2.8822"
      ]
     },
     "execution_count": 84,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df2[(df2['ANO MES'] == '2014-05') & (df2['ESTADO'] == 'SAO PAULO')]['PREÇO MÉDIO REVENDA'].mean()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "6ab2edd0-8bf7-49d7-b3e8-5535ec4a58cf",
   "metadata": {},
   "source": [
    "### 10. Você conseguiria descobrir em qual(quais) estado(s) a gasolina ultrapassou a barreira dos R$ 5,00? E quando isso ocorreu?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 100,
   "id": "32a9045a-899c-4775-8b66-c0490f3e62a7",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>ESTADO</th>\n",
       "      <th>ANO MES</th>\n",
       "      <th>PREÇO MÉDIO REVENDA</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>98201</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-05</td>\n",
       "      <td>5.053</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98347</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.035</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98493</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.038</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98511</th>\n",
       "      <td>RIO DE JANEIRO</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.016</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98646</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.031</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98797</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.036</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>98948</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-06</td>\n",
       "      <td>5.039</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99098</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-07</td>\n",
       "      <td>5.021</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99247</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-07</td>\n",
       "      <td>5.042</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99398</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-07</td>\n",
       "      <td>5.038</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99549</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-07</td>\n",
       "      <td>5.033</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99701</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-08</td>\n",
       "      <td>5.031</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>99852</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-08</td>\n",
       "      <td>5.015</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>100003</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-08</td>\n",
       "      <td>5.023</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>100153</th>\n",
       "      <td>ACRE</td>\n",
       "      <td>2018-08</td>\n",
       "      <td>5.036</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                ESTADO  ANO MES  PREÇO MÉDIO REVENDA\n",
       "98201             ACRE  2018-05                5.053\n",
       "98347             ACRE  2018-06                5.035\n",
       "98493             ACRE  2018-06                5.038\n",
       "98511   RIO DE JANEIRO  2018-06                5.016\n",
       "98646             ACRE  2018-06                5.031\n",
       "98797             ACRE  2018-06                5.036\n",
       "98948             ACRE  2018-06                5.039\n",
       "99098             ACRE  2018-07                5.021\n",
       "99247             ACRE  2018-07                5.042\n",
       "99398             ACRE  2018-07                5.038\n",
       "99549             ACRE  2018-07                5.033\n",
       "99701             ACRE  2018-08                5.031\n",
       "99852             ACRE  2018-08                5.015\n",
       "100003            ACRE  2018-08                5.023\n",
       "100153            ACRE  2018-08                5.036"
      ]
     },
     "execution_count": 100,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df2[df2['PREÇO MÉDIO REVENDA'] > 5][['ESTADO', 'ANO MES', 'PREÇO MÉDIO REVENDA']].head(15)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "80f4c3a6-ba0e-43b0-a328-91c0aa04348c",
   "metadata": {},
   "source": [
    "### 11. Qual a média de preço dos estados da região sul em 2012?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 126,
   "id": "e6bbbe89-3dc9-4264-ba31-2ce5aa76054b",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "2.7214423076923073"
      ]
     },
     "execution_count": 126,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_aux = df2[df2[\"DATA FINAL\"].apply(lambda x: x.year) == 2012]\n",
    "df_aux[df_aux['REGIÃO'] == 'SUL']['PREÇO MÉDIO REVENDA'].mean()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "28781cbf-0dba-4512-83df-87537e548c63",
   "metadata": {},
   "source": [
    "### 12. Você conseguiria obter uma tabela contendo a variação percentual ano a ano para o estado do Rio de Janeiro?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "09d2d505-127b-47ff-8fe5-0c6170da3900",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "id": "d5e51a54-13f7-4f62-9903-235ac6256b38",
   "metadata": {},
   "source": [
    "### DESAFIO: Crie uma tabela contendo uma serie temporal com a diferença absoluta e percentual entre os valores mais baratos e caros. Apresente também ao lado os estados na qual os maiores e menores preços foram registrados."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "82b2263c-99d4-47ac-a7ea-ae5f1057d71f",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.11.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
