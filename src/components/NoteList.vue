<template>
  <div class="NoteList u-absolute-flex-column">
    <header class="app-header">All Notes ({{ notesCount }})</header>
    <ul class="u-scroller">
      <li v-for="note in notes">
        <a>
          <i class="el-icon-arrow-right"></i>
          <p class="note-title">{{ note.title }}</p>
          <p class="small">{{ note.meta }}</p>
        </a>
      </li>
    </ul>
    <div class="app-controls">
      <div class="u-flex-row">
        <el-button type="primary" class="u-elastic">Add Note</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      notes: [],
    };
  },
  methods: {
    loadNotes() {
      this.notes = [
        { title: 'A new note', meta: 'Added 2 days ago' },
        { title: 'Another new note', meta: 'Added 2 days ago' },
        { title: 'And another one', meta: 'Added 2 days ago' },
        { title: 'Personal Note', meta: 'Added 1 hour ago' },
      ];
    },
  },
  mounted() {
    this.loadNotes();
  },
  computed: {
    notesCount() {
      return this.notes.length;
    },
  },
};
</script>

<style scoped>
.NoteList ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

.NoteList ul li {
  border-bottom: solid 1px #EFEFEF;
}

.NoteList ul li a {
  position: relative;
  display: block;
  padding: 12px 25px;
  cursor: pointer;
  color: #2c3e50;
  text-decoration: none;
}

.NoteList ul li a:hover {
  color: #006699;
}

.NoteList ul li a i {
  position: absolute;
  top: 22px;
  right: 25px;
  margin: auto 0;
}

.NoteList ul li a .note-title {
  width: 90%;
  margin: 0;
  font-size: 14px;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}

.NoteList ul li a .small {
  margin: 0;
  margin-top: 3px;
  font-size: 11px;
}
</style>