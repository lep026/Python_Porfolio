# Python_Porfolio
This repository showcases all the work and code that I completed in Dr. Josh Vandenbrink's  Inro Python class. 
## Jupyter_Notebooks_Parts_1_and_2 
Im Sorry Dr. Josh :( I had some difficulty with the 2nd part and so there are lots of errors :/ 

Also since you like dad jokes... How do functions break up? They stop calling each other :) 

Here is mu code!!! 

{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [],
   "source": [
    "%matplotlib inline \n",
    "import pandas as pd \n",
    "import matplotlib.pyplot as plt \n",
    "import seaborn as sns \n",
    "sns.set(style = \"darkgrid\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [],
   "source": [
    "df = pd.read_csv('/home/student/Desktop/classroom/myfiles/notebooks/fortune500.csv')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
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
       "      <th>Year</th>\n",
       "      <th>Rank</th>\n",
       "      <th>Company</th>\n",
       "      <th>Revenue (in millions)</th>\n",
       "      <th>Profit (in millions)</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>0</td>\n",
       "      <td>1955</td>\n",
       "      <td>1</td>\n",
       "      <td>General Motors</td>\n",
       "      <td>9823.5</td>\n",
       "      <td>806</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>1</td>\n",
       "      <td>1955</td>\n",
       "      <td>2</td>\n",
       "      <td>Exxon Mobil</td>\n",
       "      <td>5661.4</td>\n",
       "      <td>584.8</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>2</td>\n",
       "      <td>1955</td>\n",
       "      <td>3</td>\n",
       "      <td>U.S. Steel</td>\n",
       "      <td>3250.4</td>\n",
       "      <td>195.4</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>3</td>\n",
       "      <td>1955</td>\n",
       "      <td>4</td>\n",
       "      <td>General Electric</td>\n",
       "      <td>2959.1</td>\n",
       "      <td>212.6</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>4</td>\n",
       "      <td>1955</td>\n",
       "      <td>5</td>\n",
       "      <td>Esmark</td>\n",
       "      <td>2510.8</td>\n",
       "      <td>19.1</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   Year  Rank           Company  Revenue (in millions) Profit (in millions)\n",
       "0  1955     1    General Motors                 9823.5                  806\n",
       "1  1955     2       Exxon Mobil                 5661.4                584.8\n",
       "2  1955     3        U.S. Steel                 3250.4                195.4\n",
       "3  1955     4  General Electric                 2959.1                212.6\n",
       "4  1955     5            Esmark                 2510.8                 19.1"
      ]
     },
     "execution_count": 4,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
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
       "      <th>Year</th>\n",
       "      <th>Rank</th>\n",
       "      <th>Company</th>\n",
       "      <th>Revenue (in millions)</th>\n",
       "      <th>Profit (in millions)</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>25495</td>\n",
       "      <td>2005</td>\n",
       "      <td>496</td>\n",
       "      <td>Wm. Wrigley Jr.</td>\n",
       "      <td>3648.6</td>\n",
       "      <td>493</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>25496</td>\n",
       "      <td>2005</td>\n",
       "      <td>497</td>\n",
       "      <td>Peabody Energy</td>\n",
       "      <td>3631.6</td>\n",
       "      <td>175.4</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>25497</td>\n",
       "      <td>2005</td>\n",
       "      <td>498</td>\n",
       "      <td>Wendy's International</td>\n",
       "      <td>3630.4</td>\n",
       "      <td>57.8</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>25498</td>\n",
       "      <td>2005</td>\n",
       "      <td>499</td>\n",
       "      <td>Kindred Healthcare</td>\n",
       "      <td>3616.6</td>\n",
       "      <td>70.6</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>25499</td>\n",
       "      <td>2005</td>\n",
       "      <td>500</td>\n",
       "      <td>Cincinnati Financial</td>\n",
       "      <td>3614.0</td>\n",
       "      <td>584</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "       Year  Rank                Company  Revenue (in millions)  \\\n",
       "25495  2005   496        Wm. Wrigley Jr.                 3648.6   \n",
       "25496  2005   497         Peabody Energy                 3631.6   \n",
       "25497  2005   498  Wendy's International                 3630.4   \n",
       "25498  2005   499     Kindred Healthcare                 3616.6   \n",
       "25499  2005   500   Cincinnati Financial                 3614.0   \n",
       "\n",
       "      Profit (in millions)  \n",
       "25495                  493  \n",
       "25496                175.4  \n",
       "25497                 57.8  \n",
       "25498                 70.6  \n",
       "25499                  584  "
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.tail()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [],
   "source": [
    "df.columns = ['year', 'rank', 'company', 'revenue', 'profit']"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
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
       "      <th>year</th>\n",
       "      <th>rank</th>\n",
       "      <th>company</th>\n",
       "      <th>revenue</th>\n",
       "      <th>profit</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>0</td>\n",
       "      <td>1955</td>\n",
       "      <td>1</td>\n",
       "      <td>General Motors</td>\n",
       "      <td>9823.5</td>\n",
       "      <td>806</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>1</td>\n",
       "      <td>1955</td>\n",
       "      <td>2</td>\n",
       "      <td>Exxon Mobil</td>\n",
       "      <td>5661.4</td>\n",
       "      <td>584.8</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>2</td>\n",
       "      <td>1955</td>\n",
       "      <td>3</td>\n",
       "      <td>U.S. Steel</td>\n",
       "      <td>3250.4</td>\n",
       "      <td>195.4</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>3</td>\n",
       "      <td>1955</td>\n",
       "      <td>4</td>\n",
       "      <td>General Electric</td>\n",
       "      <td>2959.1</td>\n",
       "      <td>212.6</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>4</td>\n",
       "      <td>1955</td>\n",
       "      <td>5</td>\n",
       "      <td>Esmark</td>\n",
       "      <td>2510.8</td>\n",
       "      <td>19.1</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   year  rank           company  revenue profit\n",
       "0  1955     1    General Motors   9823.5    806\n",
       "1  1955     2       Exxon Mobil   5661.4  584.8\n",
       "2  1955     3        U.S. Steel   3250.4  195.4\n",
       "3  1955     4  General Electric   2959.1  212.6\n",
       "4  1955     5            Esmark   2510.8   19.1"
      ]
     },
     "execution_count": 7,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "25500"
      ]
     },
     "execution_count": 8,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(df)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "year         int64\n",
       "rank         int64\n",
       "company     object\n",
       "revenue    float64\n",
       "profit      object\n",
       "dtype: object"
      ]
     },
     "execution_count": 9,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.dtypes"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
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
       "      <th>year</th>\n",
       "      <th>rank</th>\n",
       "      <th>company</th>\n",
       "      <th>revenue</th>\n",
       "      <th>profit</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>228</td>\n",
       "      <td>1955</td>\n",
       "      <td>229</td>\n",
       "      <td>Norton</td>\n",
       "      <td>135.0</td>\n",
       "      <td>N.A.</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>290</td>\n",
       "      <td>1955</td>\n",
       "      <td>291</td>\n",
       "      <td>Schlitz Brewing</td>\n",
       "      <td>100.0</td>\n",
       "      <td>N.A.</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>294</td>\n",
       "      <td>1955</td>\n",
       "      <td>295</td>\n",
       "      <td>Pacific Vegetable Oil</td>\n",
       "      <td>97.9</td>\n",
       "      <td>N.A.</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>296</td>\n",
       "      <td>1955</td>\n",
       "      <td>297</td>\n",
       "      <td>Liebmann Breweries</td>\n",
       "      <td>96.0</td>\n",
       "      <td>N.A.</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>352</td>\n",
       "      <td>1955</td>\n",
       "      <td>353</td>\n",
       "      <td>Minneapolis-Moline</td>\n",
       "      <td>77.4</td>\n",
       "      <td>N.A.</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "     year  rank                company  revenue profit\n",
       "228  1955   229                 Norton    135.0   N.A.\n",
       "290  1955   291        Schlitz Brewing    100.0   N.A.\n",
       "294  1955   295  Pacific Vegetable Oil     97.9   N.A.\n",
       "296  1955   297     Liebmann Breweries     96.0   N.A.\n",
       "352  1955   353     Minneapolis-Moline     77.4   N.A."
      ]
     },
     "execution_count": 10,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "non_numeric_profits = df.profit.str.contains('[^0-9.-]') \n",
    "df.loc[non_numeric_profits].head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "{'N.A.'}"
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "set(df.profit[non_numeric_profits])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "369"
      ]
     },
     "execution_count": 13,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(df.profit[non_numeric_profits])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAXQAAAD9CAYAAACsq4z3AAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADh0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uMy4xLjEsIGh0dHA6Ly9tYXRwbG90bGliLm9yZy8QZhcZAAAS+UlEQVR4nO3de2zT1f/H8Ve72QGyZWwOLBdBCVumJqJbIMGIcRAWdRMvMSMTNBBNvKGC3ETclItSQPnGODNjjH8RTIwRHRA2EvUfEyNIQBcIEkFEN2HrNmU/2a09vz+I/cJ3a7tetrZnz0fiHztn/ex91vZFPTvncxzGGCMAQMpzJroAAEB8EOgAYAkCHQAsQaADgCUIdACwBIEOAJZID/cN7e3tWrNmjX777Te5XC5NnTpVGzduVE5OjgoKCpSfny+n8/K/C9u2bVNBQcGQFw0A6M8Rbh16R0eHTp48qdmzZ0uSPB6P/vrrL7355psqKCjQkSNHdO211w5LsQCA4MJOuWRnZwfCXJJmzpyppqamIS0KABC5sFMuV/L7/dq9e7dKSkoCbUuWLJHP59PcuXO1fPlyuVyuiApob/8/+f2ps1k1N3esvN7ORJcxrBjzyMCYU4PT6dC4cQPPioSdcrnSG2+8ofPnz+u9996T0+lUc3Oz3G63Ojs7tXr1auXn52vFihVxKxwAMHiD/oTu8Xh09uxZ1dbWBv4I6na7JUljx47Vo48+qo8//jjiArzezpT6hJ6Xl6mWlouJLmNYMeaRgTGnBqfTodzcsQP3DeYCO3fuVGNjo2pqagJTKn/99Ze6urokSX19faqvr1dhYWGcSgYARCrsJ/RTp06ptrZW06ZN06JFiyRJkydP1pNPPqmqqio5HA719fXp9ttv14svvjjkBQMABhY20GfMmKGTJ08O2FdXVxf3ggAA0WGnKABYgkAHAEsQ6ABgiYg2FgFIfZlZozUqo/9bv6fXl4BqEE8EOjDCjMpIV/nLX/Rrr3t7YQKqQTwx5QIAliDQAcASBDoAWIJABwBLEOgAYAkCHQAsQaADgCVYhw6kiGAbgrp7fMpwpfVr7+ru08W/Lw1HaUgSBDqQIkJtCArWnlpHNyBWTLkAgCUIdACwBIEOAJYg0AHAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsASBDgCWINABwBIEOgBYgkAHAEsQ6ABgCe6HDiAqwQ7c4GCNxCHQAUQl1IEbHKyRGEy5AIAlCHQAsASBDgCWCDuH3t7erjVr1ui3336Ty+XS1KlTtXHjRuXk5Ojo0aOqqqpSd3e3Jk2apO3btys3N3c46gYA/I+wn9AdDoeefPJJ1dfXq66uTlOmTNGOHTtkjNHq1atVVVWl+vp6FRcXa8eOHcNRMwBgAGEDPTs7W7Nnzw58PXPmTDU1Nemnn35SRkaGiouLJUmLFi3SgQMHhq5SAEBIEc2h+/1+7d69WyUlJWpubtbEiRMDfTk5OfL7/ero6Ih7kQCA8CJah75p0yaNGTNGixcv1sGDB+NSQG7u2LhcZzjl5WUmuoRhx5hTT0+vL+IxDPT9Pb0+ua5Ji/k6ySqVag1n0IHu8Xh09uxZ1dbWyul0yu12q6mpKdDf1tYmh8Oh7OzsiArwejvl95uIHpNIeXmZamkZWdsmGHNyiDR4XNekBd34E8xAY87Ly4zLdZJRMj7P4TidjqAfhAc15bJz5041NjaqpqZGLpdLknTrrbeqq6tLhw8fliR98sknuvfee+NUMgAgUmE/oZ86dUq1tbWaNm2aFi1aJEmaPHmyampqtG3bNlVXV1+1bBEAkBhhA33GjBk6efLkgH133HGH6urq4l4UACBy7BQFAEsQ6ABgCQIdACzB/dABSIpu3TqSC4EOQFJ069aRXJhyAQBLEOgAYAkCHQAsQaADgCUIdACwBIEOAJYg0AHAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsASBDgCWINABwBIEOgBYgkAHAEsQ6ABgCQIdACxBoAOAJQh0ALAEgQ4AliDQAcASBDoAWCI90QUAsEtPr095eZn92rt7fMpwpfVr7+ru08W/Lw1HadYj0AHEleuaNJW//EW/9rq3FwZtvzgchY0ATLkAgCUIdACwBIEOAJYY1By6x+NRfX29/vjjD9XV1Sk/P1+SVFJSIpfLpYyMDEnSqlWrdNdddw1dtQCAoAYV6PPmzdPjjz+uxx57rF/fu+++Gwh4AEDiDCrQi4uLh7oOAECMYl62uGrVKhljVFRUpJUrVyorKysedQEAIhRToO/atUtut1s9PT3asmWLNm7cqB07dkR0jdzcsbGUkBADbZqwHWPGUErk79qm5zmmQHe73ZIkl8ulyspKPfPMMxFfw+vtlN9vYiljWOXlZaqlZWRtg2DMycGm4PlfifpdJ+PzHI7T6Qj6QTjqZYv//POPLl68/Iswxmj//v0qLCyM9nIAgBgN6hP65s2b1dDQoNbWVi1dulTZ2dmqra3V8uXL5fP55Pf7NX36dFVXVw91vQCAIAYV6Bs2bNCGDRv6te/ZsyfuBQEAosNOUQCwBIEOAJYg0AHAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsASBDgCWINABwBIEOgBYIuYTiwDEV2bWaI3K4K2JyPGqAZLMqIx0lb/8Rb/2urcXJqAapBKmXADAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsASBDgCWINABwBIEOgBYgkAHAEsQ6ABgCQIdACxBoAOAJQh0ALAE90MHEoBDLDAUeEUBCRDsEAuJgywQPaZcAMASBDoAWIJABwBLEOgAYImwge7xeFRSUqKCggL9/PPPgfYzZ86ooqJCpaWlqqio0K+//jqUdQIAwggb6PPmzdOuXbs0adKkq9qrq6tVWVmp+vp6VVZWqqqqasiKBACEFzbQi4uL5Xa7r2rzer06fvy4ysrKJEllZWU6fvy42trahqZKAEBYUa1Db25u1oQJE5SWliZJSktL0/jx49Xc3KycnJyIrpWbOzaaEhIqLy8z0SUMO8YcWk+vT65r0gbdjqsl8vVl02s74RuLvN5O+f0m0WUMWl5eplpaLia6jGHFmAf3/QNtFKp7e+GA17EpROIhUa+vVHxtO52OoB+Eo1rl4na7df78efl8PkmSz+fThQsX+k3NAACGT1SBnpubq8LCQu3du1eStHfvXhUWFkY83QIAiJ+wUy6bN29WQ0ODWltbtXTpUmVnZ2vfvn16/fXXtW7dOr3//vvKysqSx+MZjnoBAEGEDfQNGzZow4YN/dqnT5+uTz/9dEiKAgBEjp2iAGAJAh0ALEGgA4AlEr4OHRgOwU4I6u7xKcM18IageOjp9bHmHMOGQMeIEOyEoLq3FwZtjwfXNWlDen3gSky5AIAlCHQAsASBDgCWINABwBIEOgBYgkAHAEuwbBFxF2zNd1d3ny7+fSkBFcVPsLEByYBXJuIu1Jrv1DpKoL9QYwMSjSkXALAEgQ4AliDQAcASBDoAWIJABwBLEOgAYAkCHQAswTp0RC3STTahDnsIdtBEsM1IkR5YESkOpkAqItARtUg32QQ77OHfx0SyGWmoD6zgYAqkIqZcAMASBDoAWIJABwBLEOgAYAkCHQAsQaADgCUIdACwRMquQ7f5VBz8Fxt87BfsOQ61SYz3+cBSNtBtPhUH/8UGH/uFeo5DbUTjfd4fUy4AYAkCHQAsQaADgCVinkMvKSmRy+VSRkaGJGnVqlW66667Yi4MABCZuPxR9N1331V+fn48LgUAiBJTLgBgibh8Ql+1apWMMSoqKtLKlSuVlZU16Mfm5o6NRwlXGep1yyNxXfRIHDOSW7xek/G4Tk+vT65r+q+ZD9Y+VGIO9F27dsntdqunp0dbtmzRxo0btWPHjkE/3uvtlN9vIv65oZ6ElpahW6Gal5c5pNdPRsHGTMgjkeLxPozX+zkvLzPoWvp454XT6Qj6QTjmKRe32y1Jcrlcqqys1JEjR2K9JAAgCjEF+j///KOLFy//62OM0f79+1VYWBiXwgAAkYlpysXr9Wr58uXy+Xzy+/2aPn26qqur41UbACACMQX6lClTtGfPnnjVAgCIAcsWAcASBDoAWIJABwBLpOz90AGMXMEOxYj04ItIrxPsYJ1kkbyVAUAQoQ7FiGQbT6TXCXWwTjJgygUALEGgA4AlCHQAsASBDgCWINABwBIEOgBYYsQsWwy2frS7x6cMV/8b0Adr7+n1DUl9AGIXbF15sPdzpNdJdiMm0EOtH420HUByCrWuPJL3c6jrJDOmXADAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsIR169ATtSEg1I3vg21qiPRm/AAQinWBnqgNAcE2Lv37s+NxM34ACIUpFwCwBIEOAJYg0AHAEgQ6AFiCQAcASxDoAGAJAh0ALGHdOvShlsiTTIJtXmKDEpCcguXFUL1nCfQIJfIkk1CnLrFBCUg+ofJiKN6zTLkAgCUIdACwBIEOAJaIOdDPnDmjiooKlZaWqqKiQr/++mscygIARCrmQK+urlZlZaXq6+tVWVmpqqqqeNQFAIhQTKtcvF6vjh8/ro8//liSVFZWpk2bNqmtrU05OTmDuobT6Yj6548fNzol2kP1RTr+eF0nUsGuPxy/o5HWnow1JVt7MtYUaXu079lQj3MYY0xUV5XU2NiotWvXat++fYG2++67T9u3b9ctt9wS7WUBAFHgj6IAYImYAt3tduv8+fPy+XySJJ/PpwsXLsjtdselOADA4MUU6Lm5uSosLNTevXslSXv37lVhYeGg588BAPET0xy6JP3yyy9at26d/v77b2VlZcnj8eimm26KV30AgEGKOdABAMmBP4oCgCUIdACwBIEOAJYg0AHAEiM+0D0ej0pKSlRQUKCff/450P7NN9/ooYceUnl5uRYvXqxz584F+rq7u1VdXa0FCxaovLxcr732WqAv2W9WFul4f//9dy1cuDDwX0lJiWbNmhV4XLKPV4ruOf7666/14IMPauHChSovL1dDQ0Ogz9Yxh+pLhTG3t7frqaeeUmlpqcrLy/X888+rra1NknT06FE98MADKi0t1bJly+T1egOPi7YvKZkR7tChQ6apqcncc8895uTJk8YYYzo6OsysWbPM6dOnjTHG7NmzxyxbtizwmE2bNpktW7YYv99vjDGmpaUl0LdkyRKzZ8+ewOOWLFkyXEMZlGjGe6XNmzebN954I/B1so/XmMjH7Pf7TXFxceB7T5w4YWbOnGl8Pp8xxs4xh3sNpMKY29vbzXfffRf4euvWreaVV14xfr/fzJ8/3xw6dMgYY0xNTY1Zt26dMcZE3ZesRnyg/+vKF/6xY8fMfffdF+hrb283+fn5xuv1ms7OTlNUVGQ6Ozv7XaO1tdUUFRWZvr4+Y4wxfX19pqioyHi93uEZRAQGO94rdXd3m9mzZ5vGxkZjTGqN15jBj9nv95tZs2aZw4cPG2OM+f77782CBQuMMfaOOVRfqo35XwcOHDBPPPGEOXbsmLn//vsD7V6v18ycOdMYY6LuS1YjfsplIDfeeKNaW1v1448/SpLq6uokSc3NzTp37pyys7P13nvv6eGHH9aSJUt0+PDhQP+ECROUlpYmSUpLS9P48ePV3NycmIEMUqjxXumrr77ShAkTAjdeS9XxSqHH7HA49J///EfPPvus7rnnHj333HPaunVroN/GMYfqS8Ux+/1+7d69WyUlJWpubtbEiRMDfTk5OfL7/ero6Ii6L1lxSPQAMjMztXPnTr311lvq7u7W3LlzlZWVpfT0dPX29urcuXO6+eabtXbtWh07dkxPP/20Dh48mOiyoxZqvFf67LPP9MgjjySoyvgKNea+vj598MEHev/991VUVKQffvhBK1asuOquoqko1JjDveZTzaZNmzRmzBgtXrw4pd+bkSLQg5gzZ47mzJkjSWptbdVHH32kKVOmqKurS+np6SorK5Mk3XbbbRo3bpzOnDmjiRMnBm5WlpaWllI3Kws23n+dP39ehw4d0rZt2wJtV96cLdXGKwUf84kTJ3ThwgUVFRVJkoqKijR69Gj98ssvmjRpkpVjDtV36dKllBqzx+PR2bNnVVtbK6fTKbfbraampkB/W1ubHA6HsrOzo+5LVky5BNHS0iLp8v+6vfPOO1q0aJHGjBmjnJwczZ49W99++62ky3/993q9mjp1akrfrCzYeP/1+eef6+6779a4ceMCbak8Xin4mK+//nr9+eefOn36tKTL9ytqbW3VDTfcYO2YQ/Wl0ph37typxsZG1dTUyOVySZJuvfVWdXV1BaZGP/nkE917770x9SWrEX8vl82bN6uhoUGtra0aN26csrOztW/fPr366qs6cuSIent7deedd2r9+vXKyMiQJJ07d07r169XR0eH0tPT9dJLL+nuu++WlPw3K4tmvJJUWlqqV199VXPnzr3qesk+Xim6MX/55Zf68MMP5XBcPh3mhRde0Pz58yXZO+ZQfakw5lOnTqmsrEzTpk3TqFGjJEmTJ09WTU2Njhw5ourqanV3d2vSpEnavn27rrvuOkmKui8ZjfhABwBbMOUCAJYg0AHAEgQ6AFiCQAcASxDoAGAJAh0ALEGgA4AlCHQAsMT/A5WUshM37b4LAAAAAElFTkSuQmCC\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "bin_sizes, _, _ = plt.hist(df.year[non_numeric_profits], bins = range(1955, 2006 ))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "/home/student/anaconda3/lib/python3.7/site-packages/pandas/core/generic.py:5208: SettingWithCopyWarning: \n",
      "A value is trying to be set on a copy of a slice from a DataFrame.\n",
      "Try using .loc[row_indexer,col_indexer] = value instead\n",
      "\n",
      "See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy\n",
      "  self[name] = value\n"
     ]
    }
   ],
   "source": [
    "df = df.loc[~non_numeric_profits] \n",
    "df.profit = df.profit.apply(pd.to_numeric)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "25131"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(df)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "year         int64\n",
       "rank         int64\n",
       "company     object\n",
       "revenue    float64\n",
       "profit     float64\n",
       "dtype: object"
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.dtypes"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 28,
   "metadata": {},
   "outputs": [
    {
     "ename": "SyntaxError",
     "evalue": "invalid syntax (<ipython-input-28-f913d30e2399>, line 1)",
     "output_type": "error",
     "traceback": [
      "\u001b[0;36m  File \u001b[0;32m\"<ipython-input-28-f913d30e2399>\"\u001b[0;36m, line \u001b[0;32m1\u001b[0m\n\u001b[0;31m    group_by_year df.loc[:, ['year', 'revenue', 'profit'].groupby('year')\u001b[0m\n\u001b[0m                   ^\u001b[0m\n\u001b[0;31mSyntaxError\u001b[0m\u001b[0;31m:\u001b[0m invalid syntax\n"
     ]
    }
   ],
   "source": [
    "group_by_year df.loc[:, ['year', 'revenue', 'profit'].groupby('year') \n",
    "avgs = group_by_year.mean() \n",
    "x = avgs.index \n",
    "y1 = avgs.profit \n",
    "def plot(x, y, ax, title, y_label): \n",
    "    as.set_title(title) \n",
    "    as.set_ylabel(y_label) \n",
    "    ax.plot(x, y) \n",
    "    ax.margrins(x = 0, y = 0)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 20,
   "metadata": {},
   "outputs": [
    {
     "ename": "SyntaxError",
     "evalue": "EOL while scanning string literal (<ipython-input-20-43bb8d8d93d0>, line 2)",
     "output_type": "error",
     "traceback": [
      "\u001b[0;36m  File \u001b[0;32m\"<ipython-input-20-43bb8d8d93d0>\"\u001b[0;36m, line \u001b[0;32m2\u001b[0m\n\u001b[0;31m    plot(x, y1, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005', 'Profit (millions')')\u001b[0m\n\u001b[0m                                                                                                           ^\u001b[0m\n\u001b[0;31mSyntaxError\u001b[0m\u001b[0;31m:\u001b[0m EOL while scanning string literal\n"
     ]
    }
   ],
   "source": [
    "fig, ax = plt.subplots() \n",
    "plot(x, y1, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005', 'Profit (millions')')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 29,
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'avgs' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "\u001b[0;32m<ipython-input-29-6f24d43dd52e>\u001b[0m in \u001b[0;36m<module>\u001b[0;34m\u001b[0m\n\u001b[0;32m----> 1\u001b[0;31m \u001b[0my2\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mavgs\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mrevenue\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      2\u001b[0m \u001b[0mfig\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0max\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mplt\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0msubplot\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      3\u001b[0m \u001b[0mplot\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mx\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0my2\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0max\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'Increase in mean Fortune 500 company revenue from 1955 to 2005'\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'Revenue (millions)'\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;31mNameError\u001b[0m: name 'avgs' is not defined"
     ]
    }
   ],
   "source": [
    "y2 = avgs.revenue \n",
    "fig, ax = plt.subplot() \n",
    "plot(x, y2, ax, 'Increase in mean Fortune 500 company revenue from 1955 to 2005', 'Revenue (millions)')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 31,
   "metadata": {},
   "outputs": [],
   "source": [
    "def plot_with_std(x, y, stds, ax, title, y_label): \n",
    "    ax.fill_between(x, y - stds, y + stds, alpha = 0.2) \n",
    "    plot(x, y, ax, title, y_label) \n",
    "    fig, (ax1, ax2) = plt.subplots(ncols = 2) \n",
    "    titile = 'Increase in main and std fortune 500 company %s from 1995 to 2005' \n",
    "    stds1 = group_by_year.std().profit.values \n",
    "    stds2 = group_by_year.std().revenue.values \n",
    "    plot_with_std(x, y1.values, stds1, ax1, title % 'profits', 'Profit (millions)')  \n",
    "    plot_with_std(x, y1.values, stds2, ax2, title % 'revenues', 'Revenue (millions)') \n",
    "    fig.set_size_inches(14,4) \n",
    "    fig.tight_layout()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
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
   "version": "3.7.4"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}

## Python_Fundamentals 
This shows all the work i did in python fundamentals 

```python
# Any python interpreter can be used as a calculator:  
3 + 4 * 5

```




    23




```python
# Lets save a value to a a variable 
weight_kg = 60
```


```python
print(weight_kg)
```

    60



```python
# Weight0 = valud 
# 0weight = invalid 
# weight and Weight are different
```


```python
# Types of data 
# There are three common types of data 
# Integer numbers 
# floating point numbers 
# Strings
```


```python
weight_kg=60.3 
# floating point
```


```python
patient_name = "John Smith" 
# String comprised of letters
```


```python
patient_id = "001"  
# String comprised of numbers

```


```python
# Use variables in python 

weight_lb = 2.2 * weight_kg 

print(weight_lb)

```

    132.66



```python
# lets add a prefix to our patient id 

patient_id = 'inflam_' + patient_id 

print(patient_id)

```

    inflam_001



```python
# Lets combine print statements 

print(patient_id, 'weight in kilograms:', weight_kg)
```

    inflam_001 weight in kilograms: 60.3



```python
# we can call a function inside another function 

print(type(60.3)) 

print(type(patient_id))
```

    <class 'float'>
    <class 'str'>



```python
# We can also do calculations inside the print function 

print('weight in lbs', 2.2 * weight_kg)
```

    weight in lbs 132.66



```python
print(weight_kg)
```

    60.3



weight_kg = 65.0 

print('weight in kilograms is now', weight_kg)
```

    weight in kilograms is now 65.0




```

## Analyzing_Patient_Data 
This showcases all the work i did for analyzing inflammation data 

```python
import numpy
```


```python
numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print('first value in data:', data[0,0])
```

    first value in data: 0.0



```python
print('middle value in data', data[29,19])
```

    middle value in data 16.0



```python
print(data[0:4, 0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10, 0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3, 36:]
```


```python
print('small is:')
```

    small is:



```python
print(small)
```

    [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python
#lets us a numpy function 

print(numpy.mean(data))
```

    6.14875



```python
maxval, minval, stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)
```


```python
print(maxval) 
print(minval) 
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
print('maximum inflammation:', maxval) 
print('minimum inflammation:', minval) 
print('standard deviation:', stdval) 
```

    maximum inflammation: 20.0
    minimum inflammation: 0.0
    standard deviation: 4.613833197118566



```python
#sometimes we want to look at variation in statistical values, such as maximum inflammation per patient or average from day one. 

pateint_0 = data[0, :] # 0 on the first axis (rows), everythingon the second (columns) 

print('maximum inflammation for patient 0:', numpy.amax(patient_0)) 


```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-28-94e5c3206992> in <module>
          3 pateint_0 = data[0, :] # 0 on the first axis (rows), everythingon the second (columns)
          4 
    ----> 5 print('maximum inflammation for patient 0', numpy.amax(patient_0))
          6 


    NameError: name 'patient_0' is not defined



```python
print('maximum inflammation for patient 2:', numpy.amax(data[2, :]))
```

    maximum inflammation for patient 2: 19.0



```python
print(numpy.mean(data, axis = 0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis = 0).shape)
```

    (40,)



```python
print(numpy.mean(data, axis = 1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]



```python

```

## Analyzing_Data_2_Data_Visualization 

```python
import numpy 
data = numpy.loadtxt(fname= 'inflammation-01.csv', delimiter = ',')
```


```python
import matplotlib.pyplot 
image = matplotlib.pyplot.imshow(data) 
matplotlib.pyplot.show()
```


![png](output_1_0.png)



```python
# average inflammation over time 

ave_inflammation = numpy.mean(data, axis = 0) 
ave_plot = matplotlib.pyplot.plot(ave_inflammation) 
matplotlib.pyplot.show()
```


![png](output_2_0.png)



```python
max_plot = matplotlib.pyplot(numpy.amax(data, axis = 0)) 
matplotlib.pyplot.show()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-10-9b3aa0a24171> in <module>
    ----> 1 max_plot = matplotlib.pyplot(numpy.amax(data, axis = 0))
          2 matplotlib.pyplot.show()


    TypeError: 'module' object is not callable



```python
min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0)) 
mtplotlib.pyplot.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-11-269fe4855bc2> in <module>
          1 min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0))
    ----> 2 mtplotlib.pyplot.show()
    

    NameError: name 'mtplotlib' is not defined



![png](output_4_1.png)



```python
import numpy 
import matplotlib.pyplot 

```


```python
fig = matplotlib.pyplot.figure(figsize = (10.0, 3.0)) 

axes1 = fig.add_subplot(1, 3, 1) 
axes2 = fig.add_subplot(1, 3, 2) 
axes3 = fig.add_subplot(1, 3, 3) 

axes1.set_ylabel('average') 
axes1.plot(numpy.mean(data, axis = 0)) 

axes2.set_ylabel('max') 
axes2.plot(numpy.amax(data, axis = 0)) 

axes3.set_ylabel('min') 
axes3.plot(numpy.amin(data, axis =0)) 

fig.tight_layout() 
matplotlib.pyplot.savefig('inflammation.png')  
matplotlib.pyplot.show()

```


![png](output_6_0.png)



```python

```
## Analyzing Data 3 

I need to go in and see what name i gave this file in jupyter  

## Storing Values in Lists 

```python
odds = [1, 3, 5, 7] 
print('odds are:', odds)
```

    odds are: [1, 3, 5, 7]



```python
print('first element:', odds[0]) 
print('last element:', odds[3]) 
print('"-1" element:', odds[-1])
```

    first element: 1
    last element: 7
    "-1" element: 7



```python
names = ['Curie', 'Darwing', 'Turing'] # typo in Darwins name 

print('names is originally:', names)  

names[1] = 'Darwin' # Correct the name  

print('final value of names:', names)
```

    names is originally: ['Curie', 'Darwing', 'Turing']
    final value of names: ['Curie', 'Darwin', 'Turing']



```python
#name = 'Darwin' 
#name[0] = 'd'
```


```python
odds.append(11) 
print('odds after adding a value:', odds)
```

    odds after adding a value: [1, 3, 5, 7, 11, 11]



```python
removed_element = odds.pop(0) 
print('odds after removing first element:', odds) 
print('removed_element:', removed_element)
```

    odds after removing first element: [3, 5, 7, 11, 11]
    removed_element: 1



```python
odds.reverse() 
print('odds after reversing:', odds)
```

    odds after reversing: [11, 11, 7, 5, 3]



```python
odds = [3,5,7] 
primes = odds 
primes.append(2) 
print('primes:', primes) 
print('odds:', odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds = [3,5,7] 
primes = list(odds) 
primes.append(2) 
print('primes:', primes)
print('odds:', odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name = "Drosophila melanogaster" 
group = binomial_name[0:10] 
print('group:', group) 

species = binomial_name[11:23] 
print('species', species) 
chromosomes = ['X', 'Y', '2', '3', '4'] 
autosomes = chromosomes[2:5] 
print('autosomes:', autosomes) 
last = chromosomes[-1] 
print('last:', last)
```

    group: Drosophila
    species melanogaster
    autosomes: ['2', '3', '4']
    last: 4



```python
date = 'Monday 4 January 2023'
day = date[0:6]
print('Using 0 to begin range:', day)
day = date[:6]
print('omitting beginning index:', day)
```

    Using 0 to begin range: Monday
    omitting beginning index: Monday



```python
months = ['jan,' 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep', 'oct', 'nov', 'dec'] 
          
sond = months[8:12] 

print('With known last position:', sond) 
sond = months[8:len(months)]  
print('Using len() to get last entry:', sond) 
sand = months[8:] 
print('Omitting ending index:', sond)
```

    With known last position: ['oct', 'nov', 'dec']
    Using len() to get last entry: ['oct', 'nov', 'dec']
    Omitting ending index: ['oct', 'nov', 'dec']



```python

```

## Using Loops 

```python
odds = [1,3,5,7] 
```


```python
print(odds[0])
print(odds[1]) 
print(odds[2]) 
print(odds[3])
```

    1
    3
    5
    7



```python
odds = [1,3,5] 
print(odds[0]) 
print(odds[1]) 
print(odds[2]) 
print(odds[3])
```

    1
    3
    5



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-70c007a0821f> in <module>
          3 print(odds[1])
          4 print(odds[2])
    ----> 5 print(odds[3])
    

    IndexError: list index out of range



```python

```


```python
odds = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19] 

for num in odds: 
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19



```python
length = 0 
names = ['Curie', 'Darwin', 'Turting'] 
for value in names: 
    length = length + 1 
print('There are', length, 'names in the list')
```

    There are 3 names in the list



```python
name = "Rosalind" 
for name in ['Curie', 'Darwin', 'Turing']: 
    print(name) 
print('after the loop, name is', name)
```

    Curie
    Darwin
    Turing
    after the loop, name is Turing



```python
print(len([0,1,2,3]))
```

    4



```python
name = ['Curie', 'Darwin','Turing'] 

print(len(name))
```

    3



```python

```

## Using Multiple Files 

```python
import glob
```


```python
print(glob.glob('inflammation*.csv'))
```

    ['inflammation-10.csv', 'inflammation-09.csv', 'inflammation-11.csv', 'inflammation-06.csv', 'inflammation-05.csv', 'inflammation-08.csv', 'inflammation-01.csv', 'inflammation-07.csv', 'inflammation-04.csv', 'inflammation-03.csv', 'inflammation-02.csv', 'inflammation-12.csv']



```python
import glob 
import numpy 
import matplolib.pyplot 

filenames = sorted(glob.glob('inflammation*.csv')) 
filenames = filenames[0:3] 

for filename in filenames: 
    print(filename) 
    
    data = numpy.load.txt(fname=filename, delimiter = ',') 
    
    fig = matplotlib.pyplot.figure(figsize = (10.0, 3.0) 
    
    axes1 = fig.add_subplot(1,3,1) 
    axes2 = fig.add_subplot(1,3,2) 
    axes3 = fig.add_subplot(1,3,3) 
    
    axes1.set_ylabel('average') 
    axes1.plot(numpy.mean(data, axis = 0)) 
    
    axes2.set_ylabel('max') 
    axes2.plot(numpy.amax(data, axis = 0))  
    
    axes3.set_ylabel('min') 
    axes3.plot(numpy.amin(data, axis = 0)) 
    
    fig.tight_layout() 
    matplotlib.pyplot.show()
```


      File "<ipython-input-8-3d286e472047>", line 15
        axes1 = fig.add_subplot(1,3,1)
            ^
    SyntaxError: invalid syntax




```python
#ask dr josh why this is not running
```


```python

```

## Making Choices 

### Making_choices_2  

```python
import numpy
```


```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter = ',')

```


```python
max_inflammation_0 = numpy.amax(data, axis = 0) 

```


```python
max_inflammation_20 = numpy.amax(data, axis = 0)[20] 

if max_inflammation_0 == 0 and max_inflammation_20 == 20: 
    print('Saspictious looking maxima!')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-7-2aaa6d4d284d> in <module>
          1 max_inflammation_20 = numpy.amax(data, axis = 0)[20]
          2 
    ----> 3 if max_inflammation_0 == 0 and max_inflammation_20 == 20:
          4     print('Saspictious looking maxima!')


    ValueError: The truth value of an array with more than one element is ambiguous. Use a.any() or a.all()



```python
elif numpy.sum(numpy.amin(data, axis = 0)) == 0: 
    print('Minima add up to zero!')
```


      File "<ipython-input-8-94b57988b22c>", line 1
        elif numpy.sum(numpy.amin(data, axis = 0)) == 0:
           ^
    SyntaxError: invalid syntax




```python
else: 
    print('seems ok')
```


      File "<ipython-input-9-a219a9d5551e>", line 1
        else:
           ^
    SyntaxError: invalid syntax




```python
data = numpy.load.txt(fname = 'inflammation-03.csv' , delimiter= ',') 

max_inflammation_0 = numpy.amax(data, axis = 0)[0] 

max_inflammation_20 = numpy.amax(data, axis = 0)[20] 

if max_inflammation_0 == and max_inflammation_20 == 20: 
    print('suspicious looking maxima') 
elif numpy.sum(numpy.amin(data, axis=0)) == 0: 
    print('minima add up to zero -> healthy person alaert') 
else: 
    print('seems ok')
```


      File "<ipython-input-11-2cbefcdf0e96>", line 7
        if max_inflammation_0 == and max_inflammation_20 == 20:
                                   ^
    SyntaxError: invalid syntax




```python

```

### Making_Choices 

```python
num = 37 
if num > 100: 
    print('greater') 
else: 
    print('not greater') 
print('done')
    

    
```

    not greater
    done



```python
num = 53 
print('before conditional...') 
if num > 100: 
    print(num, 'is greater than 100') 
print('...after conditional')
```

    before conditional...
    ...after conditional



```python
num = -3 

if num > 0: 
    print(num, 'is positive')
elif num == 0:
    print(num, 'is zero')
else: 
    print(num, 'is negative')
```

    -3 is negative



```python
if (1 > 0) and (-1 >= 0): 
    print('both parts are true')
else: 
    print('at least one part if false')
```

    at least one part if false



```python
if (-1 > 0) or (-1 >= 0): 

    print('at least one part is false') 
else: 
    print('both of these are false')
```

    both of these are false



```python
import numpy 
```


```python

```

## Functions (1,2,3,and 4) 

### Functions_Part_1 

```python
fahrenheit_val = 99 
celcius_val = ((fahrenheit_val - 32) *(5/9)) 

print(celcius_val)
```

    37.22222222222222



```python
fahrenheit_val2 = 43 
celcius_val2 = ((fahrenheit_val2 - 32) *(5/9)) 

print(celcius_val2)
```

    6.111111111111112



```python
def explicit_fahr_to_celsius(temp): 
    # Assign the converted value to variable 
    converted = ((temp - 32) * (5/9)) 
    # return the values of the new variable 
    return converted
```


```python
def fahr_to_celsius(temp): 
    # return converted values more efficiently using the return function without creating 
    # a new variable. this code does the same thing as the previous function but it is more 
    # explicit in explaining how the return commnd works. 
    return ((temp - 32) * (5/9))
```


```python
fahr_to_celsius(32) 
```




    0.0




```python
explicit_fahr_to_celsius(32)
```




    0.0




```python
print('freezing point of water:', fahr_to_celsius(32), 'C') 
print('boiling point of water:', fahr_to_celsius(221), 'C')
```

    freezing point of water: 0.0 C
    boiling point of water: 105.0 C



```python
def celsius_to_kevin(temp_c): 
    return temp_c + 273.15 

print('freezing point of water in Kelvin:' , celsius_to_kelvin(0.))
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-20-f807a024d3c1> in <module>
          2     return temp_c + 273.15
          3 
    ----> 4 print('freezing point of water in Kelvin:' , celsius_to_kelvin(0.))
    

    NameError: name 'celsius_to_kelvin' is not defined



```python
def fahr_to_kelvin(temp_f): 
    temp_c = fahr_to_celsius(temp_f) 
    temp_k = celsius_to_kelvin(temp_c) 
    return temp_k 

print('boiling point of water in kelvin:', fahr_to_kelvin(212.0))
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-18-65409be2dd2e> in <module>
          4     return temp_k
          5 
    ----> 6 print('freezing point of water in kelvin:', fahr_to_kelvin(212.0))
    

    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python
print('Again, temperature in Kelvin was:', temp_k)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-21-eed2471d229b> in <module>
    ----> 1 print('Again, temperature in Kelvin was:', temp_k)
    

    NameError: name 'temp_k' is not defined



```python
temp_kelvin = fahr_to_kelvin(212.0)
print('Temperature in Kelvin was:', temp_kelvin)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-25-aae613bdf395> in <module>
    ----> 1 temp_kelvin = fahr_to_kelvin(212.0)
          2 print('Temperature in Kelvin was:', temp_kelvin)


    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python
def print_temperature(): 
    print('Temperature in Fahrenheit was:', temp_fahr)
    print('Temperature in Kelvin was:', temp_kelvin)
    
temp_fahr = 212.0 
temp_kelvin = fahr_to_kelvin(temp_fahr) 

print_temperaturres()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-28-9371da9cb6aa> in <module>
          4 
          5 temp_fahr = 212.0
    ----> 6 temp_kelvin = fahr_to_kelvin(temp_fahr)
          7 
          8 print_temperaturres()


    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python

```
### creating-functions-part-2 

```python
import numpy  
import glob 
import matplotlib 
import matplotlib.pyplot 

```


```python
def visualize(filename): 
    
    data = numpy.loadtxt(fname = filename, delimiter = ',') 
    
    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0)) 
    
    axes1 = fig.add_subplot(1, 3, 1) 
    axes2 = fig.add_subplot(1, 3, 2) 
    axes3 = fig.add_subplot(1, 3, 3) 
    
    axes1.set_ylabel('average')  
    axes1.plot(numpy.mean(data, axis = 0)) 
    
    axes2.set_ylabel('max') 
    axes2.plot(numpy.amax(data, axis = 0)) 
    
    axes3.set_ylabel('min') 
    axes3.plot(numpy.amin(data, axis = 0)) 
    
    fig.tight_layout() 
    matplotlib.pyplot.show()
```


```python
def detect_problems(filename): 
    
    data = numpy.loadtxt(fname = filename, delimiter = ',') 
    
    if numpy.amax(data, axis = 0)[0] == 0 and numpy.amax(data, axis=0)[20] == 20: 
        print("Suspicious looking maxima") 
    elif numpy.sum(numpy.amin(data, axis = 0)) == 0: 
        print('Minimum add up to zero') 
    else: 
        print('Seems ok') 
filenames = sorted(glob.glob('inflammation*.csv'))
```


```python
filenames = sorted(glob.glob('inflammation*.csv')) 

for filename in filenames:
    print(filename) 
    visualize(filename)
    detect_problems(filename)
```

    inflammation-01.csv



![png](output_3_1.png)


    Suspicious looking maxima
    inflammation-02.csv



![png](output_3_3.png)


    Suspicious looking maxima
    inflammation-03.csv



![png](output_3_5.png)


    Minimum add up to zero
    inflammation-04.csv



![png](output_3_7.png)


    Suspicious looking maxima
    inflammation-05.csv



![png](output_3_9.png)


    Suspicious looking maxima
    inflammation-06.csv



![png](output_3_11.png)


    Suspicious looking maxima
    inflammation-07.csv



![png](output_3_13.png)


    Suspicious looking maxima
    inflammation-08.csv



![png](output_3_15.png)


    Minimum add up to zero
    inflammation-09.csv



![png](output_3_17.png)


    Suspicious looking maxima
    inflammation-10.csv



![png](output_3_19.png)


    Suspicious looking maxima
    inflammation-11.csv



![png](output_3_21.png)


    Minimum add up to zero
    inflammation-12.csv



![png](output_3_23.png)


    Suspicious looking maxima



```python
def offset_mean(data, target_mean_value): 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
z = numpy.zeros((2,2)) 
print(offset_mean(z, 3)) 

```

    [[3. 3.]
     [3. 3.]]



```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',') 

print(offset_mean(data, 0))
```

    [[-6.14875 -6.14875 -5.14875 ... -3.14875 -6.14875 -6.14875]
     [-6.14875 -5.14875 -4.14875 ... -5.14875 -6.14875 -5.14875]
     [-6.14875 -5.14875 -5.14875 ... -4.14875 -5.14875 -5.14875]
     ...
     [-6.14875 -5.14875 -5.14875 ... -5.14875 -5.14875 -5.14875]
     [-6.14875 -6.14875 -6.14875 ... -6.14875 -4.14875 -6.14875]
     [-6.14875 -6.14875 -5.14875 ... -5.14875 -5.14875 -6.14875]]



```python
print('original min, mean and max are:', numpy.amin(data), numpy.mean(data), numpy.amax(data)) 
offset_data = offset_mean(data, 0) 
print('min, mean, and max of offset data are:', 
    numpy.amin(offset_data), 
    numpy.mean(offset_data), 
    numpy.amax(offset_data))
```

    original min, mean and max are: 0.0 6.14875 20.0
    min, mean, and max of offset data are: -6.14875 2.842170943040401e-16 13.85125



```python
print('std dev before and after:', numpy.std(data), numpy.std(offset_data))
```

    std dev before and after: 4.613833197118566 4.613833197118566



```python
print('difference in standard deviation before and after:', 
      numpy.std(data) - numpy.std(offset_data))
```

    difference in standard deviation before and after: 0.0



```python
# offset_mean(data, target_mean_value): 
# return a new array containing the original data with its mean offset to match the desired value. 
# This data should be imputed as a measurement in columns and samples in rows

def offset_mean(data, target_mean_value): 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
def offset_mean(data, target_mean_value): 
    """Return a new array containing the original datra with its mean offset to match the desired value""" 
    return(data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original datra with its mean offset to match the desired value
    



```python
def offset_mean(data, target_mean_value): 
    """Return a new array containing the original data with its mean offset to match the desired value. 
    
    Examples 
    ---------- 
    
    >>> Offset_mean([1,2,3], 0) 
    array([-1., 0., 1.]) 
    """ 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original data with its mean offset to match the desired value. 
        
        Examples 
        ---------- 
        
        >>> Offset_mean([1,2,3], 0) 
        array([-1., 0., 1.])
    



```python
numpy.loadtxt('inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
def offset_mean(data, target_mean_value = 0.0): 
    """Return a new array containing the original data with its mean offset to match the desired value, (0 by default). 
    
    Examples 
    ---------- 
    
    >>> offset_mean([1,2,3]) 
    array([-1., 0., 1.]) 
    """ 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
test_data = numpy.zeros((2,2)) 
print(offset_mean(test_data, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
print(offset_mean(test_data))
```

    [[0. 0.]
     [0. 0.]]



```python
def display(a=1, b=2, c=3): 
    print('a:', a, 'b:', b, 'c:', c) 
    
    print('no parameters:') 
    display() 
    print('one parameter:') 
    display(55) 
    print('two parameters:') 
    display(55,66)
```


```python
print('only setting the value of c') 
display(c = 77)
```

    only setting the value of c
    a: 1 b: 2 c: 77
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:
    a: 1 b: 2 c: 3
    no parameters:



    ---------------------------------------------------------------------------

    RecursionError                            Traceback (most recent call last)

    <ipython-input-28-8580baa3a697> in <module>
          1 print('only setting the value of c')
    ----> 2 display(c = 77)
    

    <ipython-input-27-3c91cc97c252> in display(a, b, c)
          3 
          4     print('no parameters:')
    ----> 5     display()
          6     print('one parameter:')
          7     display(55)


    ... last 1 frames repeated, from the frame below ...


    <ipython-input-27-3c91cc97c252> in display(a, b, c)
          3 
          4     print('no parameters:')
    ----> 5     display()
          6     print('one parameter:')
          7     display(55)


    RecursionError: maximum recursion depth exceeded while calling a Python object



```python
help(numpy.loadtxt)
```

    Help on function loadtxt in module numpy:
    
    loadtxt(fname, dtype=<class 'float'>, comments='#', delimiter=None, converters=None, skiprows=0, usecols=None, unpack=False, ndmin=0, encoding='bytes', max_rows=None)
        Load data from a text file.
        
        Each row in the text file must have the same number of values.
        
        Parameters
        ----------
        fname : file, str, or pathlib.Path
            File, filename, or generator to read.  If the filename extension is
            ``.gz`` or ``.bz2``, the file is first decompressed. Note that
            generators should return byte strings for Python 3k.
        dtype : data-type, optional
            Data-type of the resulting array; default: float.  If this is a
            structured data-type, the resulting array will be 1-dimensional, and
            each row will be interpreted as an element of the array.  In this
            case, the number of columns used must match the number of fields in
            the data-type.
        comments : str or sequence of str, optional
            The characters or list of characters used to indicate the start of a
            comment. None implies no comments. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is '#'.
        delimiter : str, optional
            The string used to separate values. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is whitespace.
        converters : dict, optional
            A dictionary mapping column number to a function that will parse the
            column string into the desired value.  E.g., if column 0 is a date
            string: ``converters = {0: datestr2num}``.  Converters can also be
            used to provide a default value for missing data (but see also
            `genfromtxt`): ``converters = {3: lambda s: float(s.strip() or 0)}``.
            Default: None.
        skiprows : int, optional
            Skip the first `skiprows` lines, including comments; default: 0.
        usecols : int or sequence, optional
            Which columns to read, with 0 being the first. For example,
            ``usecols = (1,4,5)`` will extract the 2nd, 5th and 6th columns.
            The default, None, results in all columns being read.
        
            .. versionchanged:: 1.11.0
                When a single column has to be read it is possible to use
                an integer instead of a tuple. E.g ``usecols = 3`` reads the
                fourth column the same way as ``usecols = (3,)`` would.
        unpack : bool, optional
            If True, the returned array is transposed, so that arguments may be
            unpacked using ``x, y, z = loadtxt(...)``.  When used with a structured
            data-type, arrays are returned for each field.  Default is False.
        ndmin : int, optional
            The returned array will have at least `ndmin` dimensions.
            Otherwise mono-dimensional axes will be squeezed.
            Legal values: 0 (default), 1 or 2.
        
            .. versionadded:: 1.6.0
        encoding : str, optional
            Encoding used to decode the inputfile. Does not apply to input streams.
            The special value 'bytes' enables backward compatibility workarounds
            that ensures you receive byte arrays as results if possible and passes
            'latin1' encoded strings to converters. Override this value to receive
            unicode arrays and pass strings as input to converters.  If set to None
            the system default is used. The default value is 'bytes'.
        
            .. versionadded:: 1.14.0
        max_rows : int, optional
            Read `max_rows` lines of content after `skiprows` lines. The default
            is to read all the lines.
        
            .. versionadded:: 1.16.0
        
        Returns
        -------
        out : ndarray
            Data read from the text file.
        
        See Also
        --------
        load, fromstring, fromregex
        genfromtxt : Load data with missing values handled as specified.
        scipy.io.loadmat : reads MATLAB data files
        
        Notes
        -----
        This function aims to be a fast reader for simply formatted files.  The
        `genfromtxt` function provides more sophisticated handling of, e.g.,
        lines with missing values.
        
        .. versionadded:: 1.10.0
        
        The strings produced by the Python float.hex method can be used as
        input for floats.
        
        Examples
        --------
        >>> from io import StringIO   # StringIO behaves like a file object
        >>> c = StringIO(u"0 1\n2 3")
        >>> np.loadtxt(c)
        array([[0., 1.],
               [2., 3.]])
        
        >>> d = StringIO(u"M 21 72\nF 35 58")
        >>> np.loadtxt(d, dtype={'names': ('gender', 'age', 'weight'),
        ...                      'formats': ('S1', 'i4', 'f4')})
        array([(b'M', 21, 72.), (b'F', 35, 58.)],
              dtype=[('gender', 'S1'), ('age', '<i4'), ('weight', '<f4')])
        
        >>> c = StringIO(u"1,0,2\n3,0,4")
        >>> x, y = np.loadtxt(c, delimiter=',', usecols=(0, 2), unpack=True)
        >>> x
        array([1., 3.])
        >>> y
        array([2., 4.])
    



```python
numpy.loadtxt('inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python

```

what videos and see what other 2 files need to be added

## Defensive Programming 

```python
numbers = [1.5, 2.3, 0.001, 4.4] 
total = 0.0 
for num in numbers: 
    assert num > 0.0, 'Data should only contain positive values'
    total += num 
print('total is:', total)
```

    total is: 8.201



```python
numbers = [1.5, 2.3, -0.001, 4.4] 
total = 0.0 
for num in numbers: 
    assert num > 0.0, 'Data should only contain positive values'
    total += num 
print('total is:', total)
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-3-c2f302079723> in <module>
          2 total = 0.0
          3 for num in numbers:
    ----> 4     assert num > 0.0, 'Data should only contain positive values'
          5     total += num
          6 print('total is:', total)


    AssertionError: Data should only contain positive values



```python
def normalize_rectangle(rect):
    """Normalizes a rectangle so that it is at the origin and 1.0 units long on its longesr axis. insputshould be of the format (x0,, y0, x1, y1). 
    (x0, y0) and (x1, y1) define the lower left and upper right corners of the rectangle respectively""" 
    assert len(rect) == 4, 'Rectangles must contin 4 coordinates' 
    x0, y0, x1, y1 = rect 
    assert x0 < x1, 'Invalid X coordinates' 
    assert y0 < y1, 'Invalid Y coordiates' 
    
    dx = x1 - x0 
    dy = y1 - y0 
    if dx > dy:  
        scaled = dy / dx 
        upper_x, upper_y = 1.0, scaled 
    else: 
        scaled = dx / dy 
        upper_x, upper_y = scaled, 1.0 
        
    assert 0 < upper_x <= 1.0, 'Calculated upper X coordinate invalid'  
    assert 0 < upper_y <= 1.0, 'Calculated upper Y coordinate invalid' 
    
    return (0, 0, upper_x, upper_y)
```


```python
print(normalize_rectangle( 0.0, 1.0, 2.0))
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-8-e34c2165d31c> in <module>
    ----> 1 print(normalize_rectangle( 0.0, 1.0, 2.0))
    

    TypeError: normalize_rectangle() takes 1 positional argument but 3 were given



```python
print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-11-5e28a32bada1> in <module>
    ----> 1 print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
    

    <ipython-input-6-0a21467636bc> in normalize_rectangle(rect)
          4     assert len(rect) == 4, 'Rectangles must contin 4 coordinates'
          5     x0, y0, x1, y1 = rect
    ----> 6     assert x0 < x1, 'Invalid X coordinates'
          7     assert y0 < y1, 'Invalid Y coordiates'
          8 


    AssertionError: Invalid X coordinates



```python
print(normalize_rectangle((0.0, 0.0, 1.0, 5.0)))
```

    (0, 0, 0.2, 1.0)



```python
print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-13-1337bef8f4bf> in <module>
    ----> 1 print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
    

    <ipython-input-6-0a21467636bc> in normalize_rectangle(rect)
         17 
         18     assert 0 < upper_x <= 1.0, 'Calculated upper X coordinate invalid'
    ---> 19     assert 0 < upper_y <= 1.0, 'Calculated upper Y coordinate invalid'
         20 
         21     return (0, 0, upper_x, upper_y)


    AssertionError: Calculated upper Y coordinate invalid



```python

```

## Transcribing DNA to RNA 

```python
# prompt user to enter the fasta file name 

input_file_name = input("Enter the name of the input fasta file: ") 
```

    Enter the name of the input fasta file:  RARa_sequence.txt



```python
# Open the input fasta file and read the dna sequence 

with open(input_file_name, "r") as input_file: 
    dna_sequence = "" 
    for line in input_file: 
        if line.startswith(">"): 
            continue 
            
        dna_sequence += line.strip() 
        
```


```python
# transcribe the dna to rna 
rna_sequence = "" 
for nucleotide in dna_sequence: 
    if nucleotide == "T": 
        rna_sequence += "U" 
        
    else: 
        rna_sequence += nucleotide
```


```python
# Prompt the user to enter the output file name 

output_file_name = input("Enter the name of the output file:")
```

    Enter the name of the output file: RaRA_sequence2.txt



```python
# Save the RNA sequence to a text file 

with open(output_file_name, "w") as output_file: 
    output_file.write(rna_sequence) 
    print( "The RNA sequence have been saved to {output_file_name} ")
```

    The RNA sequence have been saved to {output_file_name} 



```python
print(rna_sequence)
```

    AUGGCCAGCAACAGCAGCUCCUGCCCGACACCUGGGGGCGGGCACCUCAAUGGGUACCCGGUGCCUCCCUACGCCUUCUUCUUCCCCCCUAUGCUGGGUGGACUCUCCCCGCCAGGCGCUCUGACCACUCUCCAGCACCAGCUUCCAGUUAGUGGAUAUAGCACACCAUCCCCAGCCACCAUUGAGACCCAGAGCAGCAGUUCUGAAGAGAUAGUGCCCAGCCCUCCCUCGCCACCCCCUCUACCCCGCAUCUACAAGCCUUGCUUUGUCUGUCAGGACAAGUCCUCAGGCUACCACUAUGGGGUCAGCGCCUGUGAGGGCUGCAAGGGCUUCUUCCGCCGCAGCAUCCAGAAGAACAUGGUGUACACGUGUCACCGGGACAAGAACUGCAUCAUCAACAAGGUGACCCGGAACCGCUGCCAGUACUGCCGACUGCAGAAGUGCUUUGAAGUGGGCAUGUCCAAGGAGUCUGUGAGAAACGACCGAAACAAGAAGAAGAAGGAGGUGCCCAAGCCCGAGUGCUCUGAGAGCUACACGCUGACGCCGGAGGUGGGGGAGCUCAUUGAGAAGGUGCGCAAAGCGCACCAGGAAACCUUCCCUGCCCUCUGCCAGCUGGGCAAAUACACUACGAACAACAGCUCAGAACAACGUGUCUCUCUGGACAUUGACCUCUGGGACAAGUUCAGUGAACUCUCCACCAAGUGCAUCAUUAAGACUGUGGAGUUCGCCAAGCAGCUGCCCGGCUUCACCACCCUCACCAUCGCCGACCAGAUCACCCUCCUCAAGGCUGCCUGCCUGGACAUCCUGAUCCUGCGGAUCUGCACGCGGUACACGCCCGAGCAGGACACCAUGACCUUCUCGGACGGGCUGACCCUGAACCGGACCCAGAUGCACAACGCUGGCUUCGGCCCCCUCACCGACCUGGUCUUUGCCUUCGCCAACCAGCUGCUGCCCCUGGAGAUGGAUGAUGCGGAGACGGGGCUGCUCAGCGCCAUCUGCCUCAUCUGCGGAGACCGCCAGGACCUGGAGCAGCCGGACCGGGUGGACAUGCUGCAGGAGCCGCUGCUGGAGGCGCUAAAGGUCUACGUGCGGAAGCGGAGGCCCAGCCGCCCCCACAUGUUCCCCAAGAUGCUAAUGAAGAUUACUGACCUGCGAAGCAUCAGCGCCAAGGGGGCUGAGCGGGUGAUCACGCUGAAGAUGGAGAUCCCGGGCUCCAUGCCGCCUCUCAUCCAGGAAAUGUUGGAGAACUCAGAGGGCCUGGACACUCUGAGCGGACAGCCGGGGGGUGGGGGGCGGGACGGGGGUGGCCUGGCCCCCCCGCCAGGCAGCUGUAGCCCCAGCCUCAGCCCCAGCUCCAACAGAAGCAGCCCGGCCACCCACUCCCCGUGA



```python

```


```python

```

## Translating RNA into Protein  

```python
# Promt the user to enter the input RNA file 

input_file_name = input("Enter the name of the input RNA file:")
```

    Enter the name of the input RNA file: RaRA_sequence2.txt



```python
# Open the RNA file and read the RNA sequence 

with open(input_file_name, "r") as input_file: 
    rna_sequence = input_file.read().strip()
```


```python
# Define the codon table 

codon_table = { 
    "UUU": "F", "UUC": "F", "UUA": "L", "UUG": "L",  
    "CUU": "L", "CUC": "L", "CUA": "L", "CUG": "L",
    "AUU": "I", "AUC": "I", "AUA": "I", "AUG": "M", 
    "GUU": "V", "GUC": "V", "GUA": "V", "GUG": "V",
    "UCU": "S", "UCC": "S", "UCA": "S", "UCG": "S",
    "CCU": "P", "CCC": "P", "CCA": "P", "CCG": "P",
    "ACU": "T", "ACC": "T", "ACA": "T", "ACG": "T",
    "GCU": "A", "GCC": "A", "GCA": "A", "GCG": "A", 
    "UAU": "Y", "UAC": "Y", "UAA": "*", "UAG": "*", 
    "CAU": "H", "CAC": "H", "CAA": "Q", "CAG": "Q",
    "AAU": "N", "AAC": "N", "AAA": "K", "AAG": "K",
    "GAU": "D", "GAC": "D", "GAA": "E", "GAG": "E", 
    "UGU": "C", "UGC": "C", "UGA": "*", "UGG": "W", 
    "CGU": "R", "CGC": "R", "CGA": "R", "CGG": "R", 
    "AGU": "S", "AGC": "S", "AGA": "R", "AGG": "R", 
    "GGU": "G", "GGC": "G", "GGA": "G", "GGG": "G", 
}
```


```python
# Translate RNA to protein 

protein_sequence = " " 
for i in range(0, len(rna_sequence), 3): 
    codon = rna_sequence[i:i+3] 
    if len(codon) == 3: 
        amino_acid = codon_table[codon] 
        if amino_acid == "*": 
            break  
        protein_sequence += amino_acid
        
        
```


```python
# Prompt the user to enter the output file name 

output_file_name = input("Enter the name of the output file: ")
```

    Enter the name of the output file:  RARa_Protein_Sequence.txt



```python
# Save the protein sequence to that text file 

with open(output_file_name, "w") as output_file: 
    output_file.write(protein_sequence) 
    print("The protein sequence has been saved to {output_file_name}")
```

    The protein sequence has been saved to {output_file_name}



```python
print(protein_sequence)
```

     MASNSSSCPTPGGGHLNGYPVPPYAFFFPPMLGGLSPPGALTTLQHQLPVSGYSTPSPATIETQSSSSEEIVPSPPSPPPLPRIYKPCFVCQDKSSGYHYGVSACEGCKGFFRRSIQKNMVYTCHRDKNCIINKVTRNRCQYCRLQKCFEVGMSKESVRNDRNKKKKEVPKPECSESYTLTPEVGELIEKVRKAHQETFPALCQLGKYTTNNSSEQRVSLDIDLWDKFSELSTKCIIKTVEFAKQLPGFTTLTIADQITLLKAACLDILILRICTRYTPEQDTMTFSDGLTLNRTQMHNAGFGPLTDLVFAFANQLLPLEMDDAETGLLSAICLICGDRQDLEQPDRVDMLQEPLLEALKVYVRKRRPSRPHMFPKMLMKITDLRSISAKGAERVITLKMEIPGSMPPLIQEMLENSEGLDTLSGQPGGGGRDGGGLAPPPGSCSPSLSPSSNRSSPATHSP



```python

```











