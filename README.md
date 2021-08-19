# react-super-responsive-data-table

[![Coverage Status](https://coveralls.io/repos/github/coston/react-super-responsive-data-table/badge.svg?branch=master)](https://coveralls.io/github/coston/react-super-responsive-data-table?branch=master)
[![npm downloads](https://img.shields.io/npm/dm/react-super-responsive-data-table.svg)](https://www.npmjs.com/package/react-super-responsive-data-table)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://prettier.io)

react-super-responsive-data-table converts your table data to a user-friendly list in mobile view with high performance data rendering and smart filter and sorting.

- [Installation](#installation)
- [Usage](#usage)
- [Contributors](#Contributors)
- [Contributing](#contributing)
- [License](#license)




## Installation

```
npm install react-super-responsive-data-table --save
```

## Usage

1. `import AdvancedTable from 'react-super-responsive-data-table'`
3. Write your html table with the imported components.

```jsx
import React from 'react';
import AdvancedTable from 'react-super-responsive-data-table';


() => {
  const [details, setDetails] = useState([])
  const columns = [
    {
      key: 'name',
      _style: { width: '40%' },
      _props: { color: 'primary', className: 'fw-semibold' },
    },
    'registered',
    { key: 'role', filter: false, sorter: false, _style: { width: '20%' } },
    { key: 'status', _style: { width: '20%' } },
    {
      key: 'show_details',
      label: '',
      _style: { width: '1%' },
      filter: false,
      sorter: false,
      _props: { color: 'primary', className: 'fw-semibold' },
    },
  ]
  const usersData = [
    {
      id: 0,
      name: 'John Doe',
      registered: '2018/01/01',
      role: 'Guest',
      status: 'Pending',
    },
    {
      id: 1,
      name: 'Samppa Nori',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Active',
      _props: { color: 'primary', align: 'middle' },
    },
    {
      id: 2,
      name: 'Estavan Lykos',
      registered: '2018/02/01',
      role: 'Staff',
      status: 'Banned',
      _cellProps: {
        all: { className: 'fw-semibold' },
        name: { color: 'info' },
      },
    },
    {
      id: 3,
      name: 'Chetan Mohamed',
      registered: '2018/02/01',
      role: 'Admin',
      status: 'Inactive',
    },
    {
      id: 4,
      name: 'Derick Maximinus',
      registered: '2018/03/01',
      role: 'Member',
      status: 'Pending',
    },
    {
      id: 5,
      name: 'Friderik Dávid',
      registered: '2018/01/21',
      role: 'Staff',
      status: 'Active',
    },
    {
      id: 6,
      name: 'Yiorgos Avraamu',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Active',
    },
    {
      id: 7,
      name: 'Avram Tarasios',
      registered: '2018/02/01',
      role: 'Staff',
      status: 'Banned',
      _props: { color: 'warning', align: 'middle' },
    },
    {
      id: 8,
      name: 'Quintin Ed',
      registered: '2018/02/01',
      role: 'Admin',
      status: 'Inactive',
    },
    {
      id: 9,
      name: 'Enéas Kwadwo',
      registered: '2018/03/01',
      role: 'Member',
      status: 'Pending',
    },
    {
      id: 10,
      name: 'Agapetus Tadeáš',
      registered: '2018/01/21',
      role: 'Staff',
      status: 'Active',
    },
    {
      id: 11,
      name: 'Carwyn Fachtna',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Active',
    },
    {
      id: 12,
      name: 'Nehemiah Tatius',
      registered: '2018/02/01',
      role: 'Staff',
      status: 'Banned',
    },
    {
      id: 13,
      name: 'Ebbe Gemariah',
      registered: '2018/02/01',
      role: 'Admin',
      status: 'Inactive',
    },
    {
      id: 14,
      name: 'Eustorgios Amulius',
      registered: '2018/03/01',
      role: 'Member',
      status: 'Pending',
    },
    {
      id: 15,
      name: 'Leopold Gáspár',
      registered: '2018/01/21',
      role: 'Staff',
      status: 'Active',
    },
    {
      id: 16,
      name: 'Pompeius René',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Active',
    },
    {
      id: 17,
      name: 'Paĉjo Jadon',
      registered: '2018/02/01',
      role: 'Staff',
      status: 'Banned',
    },
    {
      id: 18,
      name: 'Micheal Mercurius',
      registered: '2018/02/01',
      role: 'Admin',
      status: 'Inactive',
    },
    {
      id: 19,
      name: 'Ganesha Dubhghall',
      registered: '2018/03/01',
      role: 'Member',
      status: 'Pending',
    },
    {
      id: 20,
      name: 'Hiroto Šimun',
      registered: '2018/01/21',
      role: 'Staff',
      status: 'Active',
    },
    {
      id: 21,
      name: 'Vishnu Serghei',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Active',
    },
    {
      id: 22,
      name: 'Zbyněk Phoibos',
      registered: '2018/02/01',
      role: 'Staff',
      status: 'Banned',
    },
    {
      id: 23,
      name: 'Aulus Agmundr',
      registered: '2018/01/01',
      role: 'Member',
      status: 'Pending',
    },
    {
      id: 42,
      name: 'Ford Prefect',
      registered: '2001/05/25',
      role: 'Alien',
      status: "Don't panic!",
    },
  ]
  const getBadge = status => {
    switch (status) {
      case 'Active':
        return 'success'
      case 'Inactive':
        return 'secondary'
      case 'Pending':
        return 'warning'
      case 'Banned':
        return 'danger'
      default:
        return 'primary'
    }
  }
  const toggleDetails = index => {
    const position = details.indexOf(index)
    let newDetails = details.slice()
    if (position !== -1) {
      newDetails.splice(position, 1)
    } else {
      newDetails = [...details, index]
    }
    setDetails(newDetails)
  }
  return (
    <AdvancedTable
      sorterValue={{ column: 'name', state: 'asc' }}
      clickableRows
      onRowClick={(item, index, columnName, event) => {
        console.log(item)
        console.log(index)
        console.log(columnName)
        console.log(event)
      }}
      tableProps={{
        striped: true,
        hover: true,
      }}
      tableHeadProps={{
        color: 'danger',
      }}
      activePage={3}
      footer
      items={usersData}
      columns={columns}
      columnFilter
      tableFilter
      cleaner
      itemsPerPageSelect
      itemsPerPage={5}
      columnSorter
      pagination
      scopedColumns={{
        status: item => (
          <td>
            <CBadge color={getBadge(item.status)}>{item.status}</CBadge>
          </td>
        ),
        show_details: item => {
          return (
            <td className="py-2">
              <CButton
                color="primary"
                variant="outline"
                shape="square"
                size="sm"
                onClick={() => {
                  toggleDetails(item.id)
                }}
              >
                {details.includes(item.id) ? 'Hide' : 'Show'}
              </CButton>
            </td>
          )
        },
        details: item => {
          return (
            <CCollapse visible={details.includes(item.id)}>
              <CCardBody>
                <h4>{item.username}</h4>
                <p className="text-muted">User since: {item.registered}</p>
                <CButton size="sm" color="info">
                  User Settings
                </CButton>
                <CButton size="sm" color="danger" className="ml-1">
                  Delete
                </CButton>
              </CCardBody>
            </CCollapse>
          )
        },
      }}
    />
  )
}
```
## API
| Props  | Type | Default values |
| ------------- | ------------- | ------------- |
| activePage  | number OR undefined  | 1 |
| className  | string or undefined  |  |
| clickableRows  | boolean  |  |
| columnFilterValue  | ColumnFilterValue  |undefined  |
| footer  | boolean  |undefined  |
| header  | boolean  | undefined |
| itemsPerPage  | number  |  |
| itemsPerPageLabel  | string  | 10 |
| itemsPerPageOptions  | number[]  | [5, 10, 20, 50] |
| loading  | boolean  |  |
| noItemsLabel  | ReactNode  |  |
| onActivePageChange  | ((value: number) => void)  |  |
| onColumnFilterChange  | ((value: ColumnFilterValue) => void)  |  |
| onFilteredItemsChange  | ((items: Item[]) => void)  |  |
| onItemsPerPageChange  | ((value: number) => void)  |  |
| onRowClick  | ((item: Item, index: number, columnName: string, event: boolean  => void)  |  |
| onSorterChange  | ((value: SorterValue) => void)  |  |
| onTableFilterChange  | ((value?: string | undefined) => void)  |  |
| pagination  | boolean  |  |
| tableFilterLabel  | string  |  |
| tableFilterPlaceholder  | string  |  |
| tableFilterValue  | string  |  |


## Contributors

Super Responsive Data table Tables are made possible by these great community members:

- [dzungdinh94](https://github.com/dzungdinh94)

## Contributing

Please help turn the tables on unresponsive data! Submit an issue and/or make a pull request. Check the [projects board](https://github.com/coston/react-super-responsive-data-table/projects) for tasks to do.

## License

Licensed under the MIT license.