<template>
    <div class="avatar">
        <svg role="none" style="height:120px; width:120px">
            <mask id="circle">
            <circle cx="60" cy="60" fill="white" r="60"></circle>
            <circle cx="102" cy="102" fill="black" r="15"></circle>
            </mask>
            <g mask="url(#circle)">
            <image
                x="0"
                y="0"
                height="100%"
                preserveAspectRatio="xMidYMid slice"
                width="100%"
                xlink:href="https://images.unsplash.com/photo-1522075469751-3a6694fb2f61?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MXx8cHJvZmlsZSUyMHBpY3R1cmV8ZW58MHwyfDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"
                style="height:120px; width:120px"
            />
            <circle class="border" cx="60" cy="60" r="60"></circle>
            </g>
        </svg>
        <div class="badge" style="background: #5ad539"></div>
        <div class="name">CESAR</div>
    </div>
</template>

<script>
export default {
    name : 'Avatar'
}
</script>

<style>
.avatar {
  position: relative;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  margin-right: 12px;
  width: 120px;
}
.avatar .border {
  stroke-width: 10;
  stroke: rgba(255, 255, 255, 0.4);
  fill: none;
}
.avatar .badge {
  position: absolute;
  right: 7px;
  bottom: 27px;
  width: 22px;
  height: 22px;
  border-radius: 50%;
}

.avatar .name {
  text-align: center;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 0.8em;
  padding-top: 5px;
}
</style>