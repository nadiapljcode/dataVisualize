###Importing necessary packages

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import plotly
import plotly.express as px
import plotly.graph_objects as go


###Reading data

victims_rape = pd.read_csv('20_Victims_of_rape.csv')
victims_rape

###Checking for Null Values

print(victims_rape.isna().sum())

###Information of dataset

victims_rape.info()

###Dropping Columns

ye = victims_rape.drop("Area_Name", axis = 1)
ye.groupby(["Year"], as_index = False).sum()
ye = victims_rape.drop("Area_Name", axis = 1)
ye.groupby(["Year"], as_index = False).sum()

###Dropping Columns

*   List item
*   List item



c1 = victims_rape.drop('Subgroup' ,  axis = 1)
c2 = c1.drop('Year', axis = 1)
victims_rape1 = c2.groupby(['Area_Name'], as_index = False).sum()
victims_rape1

victims_rape1.info()

###Sorting the Data in Descending Order

sorted_data = victims_rape1.sort_values(by='Victims_of_Rape_Total', ascending=False)
sorted_data

sorted_data2 = victims_rape1.sort_values(by='Victims_Between_14-18_Yrs', ascending=False)
sorted_data2

sorted_data3 = victims_rape1.sort_values(by='Victims_Between_18-30_Yrs', ascending=False)
sorted_data3

###Pie chart

fig1 = px.pie(victims_rape1, values = "Rape_Cases_Reported", names = "Area_Name", title = "Percentage of Rape in the States and UT of India(2001-2010)", template = 'ggplot2')
fig1.update_traces(textposition = 'inside', textinfo = 'percent+label')

###2D Histogram

fig2 = px.density_heatmap(victims_rape,
                          x = "Victims_of_Rape_Total",
                          y = "Victims_Between_18-30_Yrs",
                          color_continuous_scale="Viridis", text_auto=True,
                          title = "Victims Aged 18-30", template = 'ggplot2')
fig2.show()

###Bar graph

fig3 = px.bar(sorted_data2.head(15), y='Victims_Between_14-18_Yrs',x='Area_Name',color='Victims_Between_14-18_Yrs',height=500)
fig3.update_layout(title='Number of Rape Victims (14-18 Years) Across Different Areas',xaxis_title='State/UT',yaxis_title='Victims Count',template="ggplot2")
fig3.show()

fig3_1 = px.bar(sorted_data3.head(15), y='Area_Name',x='Victims_Between_18-30_Yrs',color='Victims_Between_18-30_Yrs', orientation='h')
fig3_1.update_layout(title='15 States with the Highest Number of Rape Victims (18-30 Years)',xaxis_title='Victims Count ',yaxis_title='State/UT',template="ggplot2")
fig3_1.show()

###Parallel Coordinates Plot

fig4 = px.parallel_coordinates(victims_rape1,
                               color = "Rape_Cases_Reported",
                               dimensions=['Victims_Above_50_Yrs','Victims_Between_10-14_Yrs','Victims_Between_14-18_Yrs', 'Victims_Between_18-30_Yrs',
                                           'Victims_Between_30-50_Yrs'],
                               labels={'Victims_Above_50_Yrs': '>50 Years',
                                       'Victims_Between_10-14_Yrs': '10-14 Years',
                                       'Victims_Between_14-18_Yrs': '14-18 Years',
                                       'Victims_Between_18-30_Yrs': '18-30 Years',
                                       'Victims_Between_30-50_Yrs': '30-50 Years'},
                               color_continuous_scale='Viridis',color_continuous_midpoint=2,
                               template = "ggplot2")
fig4.update_layout(title='Rape Victims Across Age Groups and Areas',  margin=dict(t=100))
fig4.show()

###Sunburst Chart

fig5 = px.sunburst(victims_rape, path = ['Year', 'Subgroup'],
                  title = 'Victims in each Year',
                  values = 'Rape_Cases_Reported',
                  template = "ggplot2")

fig5.show()

###Line Chart

state = victims_rape[victims_rape["Area_Name"] == "Madhya Pradesh"]
fig6 = px.line(state, x = 'Year',
               y = 'Rape_Cases_Reported', markers = True,
               title = 'Rape Cases Reported in Madhya Pradesh from 2000-2010',
               template = "ggplot2")

fig6.update_layout(xaxis_title='Year', yaxis_title='Rape Cases Reported')
fig6.show()


fig6_1 = px.line(sorted_data, x = "Area_Name", y = "Victims_of_Rape_Total", markers = True, template = "seaborn")
fig6_1.update_layout(xaxis_title = "Area Name", yaxis_title = "Total Victims", title = "Line Chart Depicting the Total Rape Victims Across India")
fig6_1.show()


import plotly.offline as pyo
s1 = go.Scatter(
                    x = victims_rape1['Area_Name'], #x-axis values
                    y = victims_rape1['Rape_Cases_Reported'],#y-axis values
                    mode = "lines+markers",#mode of plot
                    name = "Rape_Cases_Reported",#name to be displayed
                     marker = {
                          'size': 10,
                          'color': 'pink',
                           'symbol': 'pentagon',
                          'line': {'width': 2}
                            },#marker color
                    text= 'Rape_Cases_Reported')#text to be displayed while clicking on point

s2 = go.Scatter(
                    x = victims_rape1['Area_Name'],#x-axis values
                    y = victims_rape1['Victims_Above_50_Yrs'],#y-axis values
                    mode = "lines+markers",
                    name = "Victims_Above_50_Yrs",
                    marker = {
                          'size': 10,
                          'color': 'red',
                           'symbol': 'pentagon',
                          'line': {'width': 2}
                            },
                    text= 'Victims_Above_50_Yrs')
s3 = go.Scatter(
                    x = victims_rape1['Area_Name'],
                    y = victims_rape1['Victims_Between_10-14_Yrs'],
                    mode = "lines+markers",
                    name = "Victims_Between_10-14_Yrs",
                    marker = {
                          'size': 8,
                          'color': 'blue',
                           'symbol': 'pentagon',
                          'line': {'width': 2}
                            },
                    text= 'Victims_Between_10-14_Yrs')

s4 = go.Scatter(
                    x = victims_rape1['Area_Name'],
                    y = victims_rape1['Victims_Between_30-50_Yrs'],
                    mode = "lines+markers",
                    name = "Victims_Between_30-50_Yrs",
                    marker = {
                          'size': 8,
                          'color': 'green',
                           'symbol': 'pentagon',
                          'line': {'width': 2}
                            },

                    text= 'Victims_Between_30-50_Yrs')


data = [s1,s2,s3,s4]
layout = go.Layout(title = 'Victims of Rape Across India of different Age Groups',
               xaxis = {'title': 'State/UT'},
              yaxis = {'title': 'Victims'},
                   template="ggplot2")
fig6_2 = go.Figure(data = data, layout = layout)
fig6_2.show()

###Bubble plot

# Bubble Chart using Plotly
fig7 = px.scatter(sorted_data, x="Rape_Cases_Reported", y="Victims_Between_30-50_Yrs",size='Victims_Between_30-50_Yrs',
	               color="Victims_Between_30-50_Yrs",
                 hover_name="Area_Name", log_x=False, size_max=60)
fig7.update_layout(title='Rape Cases Reported vs Victims between 30-50 Years',xaxis_title='Cases',yaxis_title='Victims',template="ggplot2")
fig7.show()

fig7_1 = px.scatter(ye, x = "Rape_Cases_Reported", y = "Victims_Between_30-50_Yrs", size = "Victims_Between_30-50_Yrs",
                    animation_frame="Year", animation_group="Victims_Between_30-50_Yrs",
                    color = "Victims_Between_30-50_Yrs", log_x=True, size_max=80, range_x=[100,2000], range_y=[0,800])
fig7_1.update_layout(title='Rape Cases Reported vs Victims between 30-50 Years from 2001-10',xaxis_title='Cases',yaxis_title='Victims',template="ggplot2")
fig7_1.show()

#### 3D Scatter


import plotly.express as px
fig8 = px.scatter_3d(sorted_data.head(20), x='Area_Name', y= 'Victims_Between_18-30_Yrs', z='Victims_of_Rape_Total',
              color='Area_Name')
fig8.update_layout(title='20 States/UT with the Highest Number of Total Victims & Victims Aged 18-30', autosize=True,
                   margin=dict(l=65, r=50, b=65, t=90), height = 700,
                   template="ggplot2")
fig8.show()

#### 3D Mesh Plot

import plotly.graph_objects as go

fig8_1 = go.Figure(data=[go.Mesh3d(x= ye['Year'],
                   y = victims_rape['Rape_Cases_Reported'],
                   z = victims_rape['Victims_Upto_10_Yrs'],
                   opacity=0.5,
                   color='rgba(200, 100, 225, 0.6)'
                  )])
fig8_1.update_layout(title='Cases Reported vs. Victims Upto 10 from 2001-2010', autosize = True,
                    scene = dict(
                    xaxis_title='Year',
                    yaxis_title='Rape_Cases_Reported',
                    zaxis_title='Victims_Upto_10_Yrs'),
                    height = 700, template = 'ggplot2',
                    margin=dict(l=65, r=50, b=65, t=90))
fig8_1.show()

#### 3D Bubble Chart

import plotly.graph_objects as go

start, end = 0, 10

fig8_2 = go.Figure(data=go.Scatter3d(
    x=sorted_data['Area_Name'][start:end],
    y=sorted_data['Victims_Between_30-50_Yrs'][start:end],
    z=sorted_data['Victims_Between_10-14_Yrs'][start:end],
    #text=sorted_data['Rape_Cases_Reported'][start:end],
    mode='markers',
    marker=dict(
        sizemode='diameter',
        sizeref=80,
        size=sorted_data['Victims_Between_30-50_Yrs'][start:end],
        color = sorted_data['Victims_of_Rape_Total'][start:end],
        colorscale = 'Inferno',
        colorbar_title = 'Total<br>Count',
        line_color='rgb(140, 140, 170)'
    )
))


fig8_2.update_layout(height=800, width=800,
                  title='Examining Count of Victims Aged 30-50 & 10-14 Yrs',
                  scene = dict(
                  xaxis_title = "Area Name",
                  yaxis_title = "Victims aged 30-50",
                  zaxis_title = "Victims aged 10-14"),
                  template = 'ggplot2')

fig8_2.show()

###Box Plot

#Area_Name	Rape_Cases_Reported	Victims_Above_50_Yrs	Victims_Between_10-14_Yrs
#Victims_Between_14-18_Yrs	Victims_Between_18-30_Yrs	Victims_Between_30-50_Yrs	Victims_of_Rape_Total	Victims_Upto_10_Yrs
box1 = go.Box(
                #x = least10.index,
                y = sorted_data.head(15)['Rape_Cases_Reported'],#yaxis
                name = "Cases Reported",#name
                marker = dict(color = 'blue',
                             line=dict(color='rgb(0,0,0)',width=1)),#marker properties
                text = sorted_data.head(15)['Area_Name'],#text to be displayed
                boxpoints = 'all',#scatter points
                jitter = 0.8,
                pointpos = -2
                )

data = [box1]
layout = go.Layout(autosize=False,title = 'Total Cases Reported (Top 15 States/UT) ',
              xaxis= dict(title= '',ticklen= 100),
              yaxis= dict(title= 'Number of Victims',ticklen= 5) ,
              template="ggplot2")

fig9 = go.Figure(data=data, layout=layout)
fig9.show()

###Filled Area Plot

import plotly.express as px

# Assuming sorted_data is your DataFrame
fig10 = px.area(victims_rape, x="Year", y="Victims_Upto_10_Yrs", color="Subgroup", line_group="Area_Name", template="ggplot2")
fig10.update_layout(title="Victims upto 10 Years in the States/UT of India", xaxis_title="States/UT", yaxis_title="Number of Victims")
fig10.show()


#### Dashboard

pip install dash

import dash
from dash import html   #to need to code html components
import dash_core_components as dcc
import plotly.graph_objects as go
import plotly.express as px
from dash.dependencies import Input, Output
from plotly.subplots import make_subplots

external_stylesheets = ['https://codepen.io/chriddyp/pen/bWLwgP.css']

app = dash.Dash(__name__, external_stylesheets=external_stylesheets)

colors = {
    'background': '#87CEEB',
    'text': '#111111',
    'text2': '#808080'}

app.layout = html.Div(style={'backgroundColor': colors['background']}, children=[
    html.H1(children='VICTIMS OF RAPE IN INDIA (2001-2010)',
            style={'textAlign': 'center',
                   'color': colors['text']}),
    html.Div(children='By Nadia Shaikh', style={'textAlign': 'center','color': colors['text2']}),
    html.Div(dcc.Dropdown(id='dropdown_1',options=[{'label': 'Pie Chart Repr of Total Percentages of Rape','value':'A'},
                                                   {'label': '2D Hist Repr of Victims Aged 18-30 Yrs vs. Total Victims','value':'B'},
                                                   {'label': 'Bar Graph Repr of Victims Aged 14-18 Yrs','value':'C'},
                                                   {'label': 'Horizontal Bar Graph Repr of Top 15 States (18-30 Yrs)','value':'D'},
                                                   {'label': 'Parallel Coord: Victims Across India of Diff Ages','value':'E'},
                                                   {'label': 'Sunburst Chart Showing Victims in Each Year','value':'F'},
                                                   {'label': 'Line Chart Showing Cases in MP','value':'G'},
                                                   {'label': 'Line Chart: Total Victims Across India','value':'H'},
                                                   {'label': 'Line Chart: Victims of Diff Age Groups ','value':'I'},
                                                   {'label': 'Bubble Chart: Cases Reported vs. Victims 18-30 Yrs','value':'J'},
                                                   {'label': 'Animated: Cases Repored vs Victims 30-50 Yrs','value':'K'},
                                                   {'label': '3D Chart: 20 States/UT with Highest Victims and Victims 18-30 Yrs','value':'L'},
                                                   {'label': '3D Axes: Cases Reported vs. Victims Aged Upto 10','value':'O'},
                                                   {'label': '3D Bubble: Count of Victims Aged 30-50 & 10-14 Yrs','value':'P'},
                                                   {'label': 'Box Plot: Total Cases Reported','value':'M'},
                                                   {'label': 'Filled Area Plot: Victims Upto 10','value':'N'}],
                                                    placeholder="Select an Option"),
                                                    style={'color':'black','text-align':'center',
                                                           'backgroundColor': colors['background'],
                                                           'border-style': 'double','display':'inline-block','width':'50%'}),
    dcc.Graph(id='firstgraph1',figure=fig1,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph2',figure=fig2,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph3',figure=fig3,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph4',figure=fig3_1,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph5',figure=fig4,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph6',figure=fig5,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph7',figure=fig6,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph8',figure=fig6_1,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph9',figure=fig6_2,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph10',figure=fig7,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgrap11',figure=fig8,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgrap14',figure=fig8_1,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgrap15',figure=fig8_2,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph12',figure=fig9,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']}),
    dcc.Graph(id='firstgraph13',figure=fig10,style={'width':'80%','display':'inline-block','backgroundColor': colors['background']})])
@app.callback(
    Output('firstgraph1','figure'),
    [Input('dropdown_1','value')])

def update_figure(graphtype):
    global fig
    if graphtype=='A':
        fig=go.Figure(px.pie(victims_rape1, values = "Rape_Cases_Reported", names = "Area_Name", title = "Percentage of Rapes in the States & UT of India(2001-2010)", template = 'ggplot2'))
        fig.update_traces(textposition = 'inside', textinfo = 'percent+label')
    if graphtype=='B':
        fig=go.Figure(px.density_heatmap(victims_rape,
                          x = "Victims_of_Rape_Total",
                          y = "Victims_Between_18-30_Yrs",
                          color_continuous_scale="Viridis", text_auto=True,
                          title = "Victims Aged 18-30", template = 'ggplot2'))
    if graphtype=='C':
        fig=go.Figure(px.bar(sorted_data2.head(15), y='Victims_Between_14-18_Yrs',x='Area_Name',color='Victims_Between_14-18_Yrs',height=500))
        fig.update_layout(title='Number of Rape Victims (14-18 Years) Across Different Areas',xaxis_title='State/UT',yaxis_title='Victims Count',template="ggplot2")
    if graphtype=='D':
        fig=go.Figure(px.bar(sorted_data3.head(15), y='Area_Name',x='Victims_Between_18-30_Yrs',color='Victims_Between_18-30_Yrs', orientation='h'))
        fig.update_layout(title='15 States with the Highest Number of Rape Victims (18-30 Years)',xaxis_title='Victims Count ',yaxis_title='State/UT',template="ggplot2")
    if graphtype=='E':
        fig=go.Figure(px.parallel_coordinates(victims_rape1,
                               color = "Rape_Cases_Reported",
                               dimensions=['Victims_Above_50_Yrs','Victims_Between_10-14_Yrs','Victims_Between_14-18_Yrs', 'Victims_Between_18-30_Yrs',
                                           'Victims_Between_30-50_Yrs'],
                               labels={'Victims_Above_50_Yrs': '>50 Years',
                                       'Victims_Between_10-14_Yrs': '10-14 Years',
                                       'Victims_Between_14-18_Yrs': '14-18 Years',
                                       'Victims_Between_18-30_Yrs': '18-30 Years',
                                       'Victims_Between_30-50_Yrs': '30-50 Years'},
                               color_continuous_scale='Viridis',color_continuous_midpoint=2,
                               template = "ggplot2"))
        fig.update_layout(title='Rape Victims Across Age Groups and Areas',  margin=dict(t=100))
    if graphtype=='F':
        fig=go.Figure(px.sunburst(victims_rape, path = ['Year', 'Subgroup'],
                  title = 'Victims in each Year',
                  values = 'Rape_Cases_Reported',
                  template = "ggplot2"))
    if graphtype=='G':
        state = victims_rape[victims_rape["Area_Name"] == "Madhya Pradesh"]
        fig=go.Figure(px.line(state, x = 'Year',
               y = 'Rape_Cases_Reported', markers = True,
               title = 'Rape Cases Reported in Madhya Pradesh from 2000-2010',
               template = "ggplot2"))
        fig.update_layout(xaxis_title='Year', yaxis_title='Rape Cases Reported')
    if graphtype=='H':
        fig=go.Figure(px.line(sorted_data, x = "Area_Name", y = "Victims_of_Rape_Total", markers = True, template = "seaborn"))
        fig.update_layout(xaxis_title = "Area Name", yaxis_title = "Total Victims", title = "Line Chart Depicting the Total Rape Victims Across India")
    if graphtype=='I':
        s1 = go.Scatter(
                    x = victims_rape1['Area_Name'], #x-axis values
                    y = victims_rape1['Rape_Cases_Reported'],#y-axis values
                    mode = "lines+markers",#mode of plot
                    name = "Rape_Cases_Reported",#name to be displayed
                     marker = {
                          'size': 10,
                          'color': 'pink',
                           'symbol': 'pentagon',
                          'line': {'width': 2}
                            },#marker color
                    text= 'Rape_Cases_Reported')#text to be displayed while clicking on point
        s2 = go.Scatter(
        x = victims_rape1['Area_Name'],#x-axis values
        y = victims_rape1['Victims_Above_50_Yrs'],#y-axis values
        mode = "lines+markers",
        name = "Victims_Above_50_Yrs",
        marker = {'size': 10,'color': 'red','symbol': 'pentagon','line': {'width': 2}},
        text= 'Victims_Above_50_Yrs')
        s3 = go.Scatter(
        x = victims_rape1['Area_Name'],
        y = victims_rape1['Victims_Between_10-14_Yrs'],
        mode = "lines+markers",
        name = "Victims_Between_10-14_Yrs",
        marker = {'size': 8, 'color': 'blue','symbol': 'pentagon','line': {'width': 2} },
        text= 'Victims_Between_10-14_Yrs')
        s4 = go.Scatter(x = victims_rape1['Area_Name'],y = victims_rape1['Victims_Between_30-50_Yrs'],mode = "lines+markers",
        name = "Victims_Between_30-50_Yrs",
        marker = {'size': 8,'color': 'green','symbol': 'pentagon','line': {'width': 2} },
        text= 'Victims_Between_30-50_Yrs')
        data = [s1,s2,s3,s4]
        layout = go.Layout(title = 'Victims of Rape Across India of different Age Groups',
        xaxis = {'title': 'State/UT'},
        yaxis = {'title': 'Victims'},
        template="ggplot2")
        fig = go.Figure(data = data, layout = layout)
    if graphtype=='J':
        fig=go.Figure(px.scatter(sorted_data, x="Rape_Cases_Reported", y="Victims_Between_30-50_Yrs",size='Victims_Between_30-50_Yrs',
	               color="Victims_Between_30-50_Yrs",
                 hover_name="Area_Name", log_x=False, size_max=60))
        fig.update_layout(title='Rape Cases Reported vs Victims between 30-50 Years',xaxis_title='Cases',yaxis_title='Victims',template="ggplot2")
    if graphtype=='K':
        fig=go.Figure(px.scatter(ye, x = "Rape_Cases_Reported", y = "Victims_Between_30-50_Yrs", size = "Victims_Between_30-50_Yrs",
                    animation_frame="Year", animation_group="Victims_Between_30-50_Yrs",
                    color = "Victims_Between_30-50_Yrs", log_x=True, size_max=80, range_x=[100,2000], range_y=[0,800]))
        fig.update_layout(title='Rape Cases Reported vs Victims between 30-50 Years from 2001-10',xaxis_title='Cases',yaxis_title='Victims',template="ggplot2")
    if graphtype=='L':
        fig=go.Figure(px.scatter_3d(sorted_data.head(20), x='Area_Name', y= 'Victims_Between_18-30_Yrs', z='Victims_of_Rape_Total',
              color='Area_Name'))
        fig.update_layout(title='20 States with the Highest Number of Total Victims & Victims Aged 18-30', autosize=True,margin=dict(l=65, r=50, b=65, t=90), height = 700,template="ggplot2")
    if graphtype=='M':
        box1 = go.Box(
                #x = least10.index,
                y = sorted_data.head(15)['Rape_Cases_Reported'],#yaxis
                name = "Cases Reported",#name
                marker = dict(color = 'blue',
                             line=dict(color='rgb(0,0,0)',width=1)),#marker properties
                text = sorted_data.head(15)['Area_Name'],#text to be displayed
                boxpoints = 'all',#scatter points
                jitter = 0.8,
                pointpos = -2
                )
        data = [box1]
        layout = go.Layout(autosize=False,title = 'Total Cases Reported (Top 15 States/UT) ',
              xaxis= dict(title= '',ticklen= 100),
              yaxis= dict(title= 'Number of Victims',ticklen= 5) ,
              template="ggplot2")
        fig = go.Figure(data=data, layout=layout)
    if graphtype=='N':
        fig=go.Figure( px.area(victims_rape, x="Year", y="Victims_Upto_10_Yrs", color="Subgroup", line_group="Area_Name", template="ggplot2"))
        fig.update_layout(title="Victims upto 10 Years in the States/UT of India", xaxis_title="States/UT", yaxis_title="Number of Victims")
    if graphtype=='O':
        fig=go.Figure(data=[go.Mesh3d(x= ye['Year'],
                   y = victims_rape['Rape_Cases_Reported'],
                   z = victims_rape['Victims_Upto_10_Yrs'],
                   opacity=0.5, color='rgba(200, 100, 225, 0.6)')])
        fig.update_layout(title='Cases Reported vs. Victims Upto 10 from 2001-2010', autosize = True,
                    scene = dict(xaxis_title='Year', yaxis_title='Rape_Cases_Reported',
                    zaxis_title='Victims_Upto_10_Yrs'), height = 700, template = 'ggplot2',
                    margin=dict(l=65, r=50, b=65, t=90))
    if graphtype=='P':
        fig=go.Figure(data=go.Scatter3d(
        x=sorted_data['Area_Name'][start:end], y=sorted_data['Victims_Between_30-50_Yrs'][start:end],
        z=sorted_data['Victims_Between_10-14_Yrs'][start:end],
        mode='markers',
        marker=dict(
        sizemode='diameter',
        sizeref=80,
        size=sorted_data['Victims_Between_30-50_Yrs'][start:end],
        color = sorted_data['Victims_of_Rape_Total'][start:end],
        colorscale = 'Inferno',
        colorbar_title = 'Total<br>Count',
        line_color='rgb(140, 140, 170)')))
        fig.update_layout(height=800, width=800,
                  title='Examining Count of Victims Aged 30-50 & 10-14 Yrs',
                  scene = dict(
                  xaxis_title = "Area Name",
                  yaxis_title = "Victims aged 30-50",
                  zaxis_title = "Victims aged 10-14"),
                  template = 'ggplot2')
    return fig




if __name__ == '__main__':
    app.run_server()

