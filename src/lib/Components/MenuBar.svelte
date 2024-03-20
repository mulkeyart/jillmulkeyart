<script>
  import {
    Collapse,
    NavbarToggler,
    NavbarBrand,
    Nav,
    Navbar,
    NavItem,
    NavLink,
    Dropdown,
    DropdownToggle,
    DropdownMenu,
    DropdownItem
  } from '@sveltestrap/sveltestrap';

  let isOpen = false;

  function handleUpdate(event) {
    isOpen = event.detail.isOpen;
  }
</script>

<Navbar color="dark" theme="dark" expand="md" container="md">
  <NavbarBrand href="/" class="logo">
    <img src="jillEye.jpeg" alt="eye" width="30px" height="30px"/>
    <span>jillmulkeyart</span>
  </NavbarBrand>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
  <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
    <Nav class="ms-auto" navbar>
      <NavItem>
        <NavLink href="/paintings">Paintings</NavLink>
      </NavItem>
      <NavItem>
        <NavLink href="/misc">Misc</NavLink>
      </NavItem>
      <Dropdown nav inNavbar>
        <DropdownToggle nav caret>Cart</DropdownToggle>
        <DropdownMenu end>
          <DropdownItem>To your cart</DropdownItem>
          <DropdownItem>Option 2</DropdownItem>
          <DropdownItem divider />
          <DropdownItem>Reset</DropdownItem>
        </DropdownMenu>
      </Dropdown>
    </Nav>
  </Collapse>
</Navbar>


<style>
  .logo {
    display: inline-flex;
    flex-direction: row;
    row-gap: 4px;
  }
</style>

