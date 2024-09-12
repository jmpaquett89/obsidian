<%\*
let title = tp.file.title;

    if (title.startsWith("Untitled")) {
    	title = await tp.system.prompt("Project Name");
    	await tp.file.rename(`Software Project Overview - ${title}`)
    }

    const properties = [
    	{
    		label: "Project Name",
    		value: title,
    	},
    	{
    		label: "Created",
    		value: tp.file.creation_date(),
    	},
    	{
    		label: "Modified",
    		value: tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss"),
    	},
    	{
    		label: "Author",
    		value: "{{ your name here }}",
    	},
    ];

    tR += "---"

    properties.forEach(({label, value}) => {
    	tR += `\n${label}: ${value}`
    });

    tR += "\n---"

%>

# <%\* tR += title %>

## Introduction

## Problem

## Target Audience

## Key Features

## Technology Stack
